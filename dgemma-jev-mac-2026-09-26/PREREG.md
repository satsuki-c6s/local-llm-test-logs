# PREREG — DiffusionGemma を Jev として使う (razorback16/openjev 0.3.0)

凍結: 2026-09-22 (測定開始前)。結果を見てから閾値・条件・問題セットを動かさない。

## 対象
- repo: razorback16/openjev HEAD e04794a (Apache-2.0)。公式 Docker イメージ `razorback16/openjev:0.3.0`
- モデル: 既定 `nvidia/diffusiongemma-26B-A4B-it-NVFP4` (イメージの既定値をそのまま使う)
- 機械: RTX 5090 32GB (sm_120)・ドライバ 616.92・Docker Desktop (WSL2)
- 隔離: host のディレクトリはマウントしない。HF キャッシュは専用の Docker ボリューム。ポートは 127.0.0.1 のみ
- 設定: README の既定値のまま (canvas 64、GPU_UTIL 0.9、自動の読み直しあり)。測定中は Ollama などほかの GPU 処理を止める

## 問題セット (前回 openjev 回で凍結したものを変更せずに使う)
<作業フォルダ>
- authored144 (repo/benchmarks/data/authored144.jsonl) — 前回 Qwen 版 direct = 0.813
- wanli256 (built/wanli256.jsonl) — 前回 0.629
- typesafe102 (built/typesafe102.jsonl) — 本物 Jev・Claude Opus 5・GPT-5.6 Sol の公開分布付き

## 変換 (結果を見る前に固定)
1 行 = 1 リクエスト `POST /v1/systemone`:
`{"model":"openjev-latest","state": row.state,"questions":{"q":{"type":"choice","instructions": row.question,"criteria":{opt.id: opt.description ...}}}}`
返ってきた `probabilities` を row.options の順に並べ替え、`{id, option_ids, probabilities}` で保存。追加の拡張 (steps/samples/think) は使わない。
失敗・400 の行は「未回答」として数え、除外率を併記する。

## D1 起動
- 手順: README の `docker run` どおり (ボリュームのみ差し替え)。/health が通るまでの時間・VRAM・イメージ容量・重み容量を記録
- README の例 3 問 (urgent / team / tone) を送る
- 合格: 起動して /v1/systemone が答える。例 3 問の argmax が README (urgent ≥ 0.5・team = outage・tone = furious) と一致したかは別に記録

## D2 精度
- 3 セットを全行、**3 回**通す (読み直しの乱数で答えが揺れるかを見る)
- 採点は前回の `benchmarks/evaluate.py` (mean_family_balanced_accuracy) と `evaluate_external.py --source typesafe` をそのまま使う
- 主判定: authored144 の 3 回平均が **0.75 以上** (前回と同じ線)
- 比較: 前回 Qwen 版 direct との差は evaluate.py の対比較 (group bootstrap) で CI が 0 をまたぐなら「差は言えない」
- typesafe102: 本物 Jev との最頻答え一致率と TV 距離を報告 (閾値なし)。n=102 なので割合には二項 SE を付ける
- wanli256: 報告のみ (判定に使わない。前回と同じ扱い)
- 3 回の間で argmax が変わった行の数を報告

## D3 速さ
- 同時 1/16/32/64、1 リクエスト 3 問 (README の例 3 問、state は毎回変えてキャッシュを避ける)、各 200 リクエスト。req/s・p50・p95
- README 表 (RTX PRO 6000・同時 1 で 10.7 req/s / 94 ms) との比を報告 (合否なし。機械と GPU 割当が違う)
- 読み vs 文章生成: authored144 を同時 1 で、(a) /v1/systemone、(b) 同じサーバの /v1/chat/completions に「選択肢 id を JSON で 1 つ返せ」と生成させる。交互に各 3 回、全体時間の中央値の比。(b) の正答率も記録 (JSON が壊れた行は不正解扱い・件数を併記)
- 合格: 読みが生成の **3 倍以上** 速い (前回と同じ線)

## 総合判定
- ◎: D1 合格 かつ authored144 ≥ 0.75 かつ 読み/生成 ≥ 3 倍
- ○: 3 つのうち 2 つ
- △: 1 つ以下
- 起動しない場合は × として原因を記録

## 言えないこと (先に書く)
- 本物 Jev との速さ比較 (Jev は API のみ・未契約)
- 論文・ツイートの主張の一般的な正しさ (問題セットは 3 種のみ)
- NVFP4 以外の精度 (bf16 は 5090 に載らない)
- n が小さい: authored144 は 144 問・family 別はさらに少ない

## 自己懐疑の予定
結果が良すぎ/悪すぎたら、先に変換 (選択肢の並び替え・id とラベルの対応) のバグを疑い、数行を手で突き合わせる。

## 追記 (2026-09-22 13:20Z・測定開始前) — 実行環境の変更
RTX 5090 (Docker/WSL2) では vLLM 起動中に PC がブルースクリーン (0x00020001 HYPERVISOR_ERROR) で 2 回落ちたため、同じ経路の 3 回目は行わない。
測定は README の Apple silicon 経路に切り替える: Mac mini M1 Pro 32GB・`OPENJEV_BACKEND=mlx`・既定重み `mlx-community/diffusiongemma-26B-A4B-it-4bit`・openjev e04794a・mlx-vlm 0.6.15。
- 精度の閾値・問題セット・変換は変更しない (D2 の 0.75、D3 の 3 倍)
- D3 の同時数の比較先は README の MLX 記述 (M4 Max 0.39 秒/3 問・16 同時で約 4 req/s) に読み替える。5090 の値は「起動できず」と記録
- 5090 側の記録 (6 回の起動と 2 回のクラッシュ) は times.txt と RESULTS に残す

## 追記 (2026-09-22 14:05Z・D2 1 回目の途中) — 回数の変更
typesafe102 は state が長く 1 問 23 秒 (102 問で約 40 分)。3 回で 2 時間になるため **typesafe102 だけ 1 回** にする。閾値は無い集合。authored144 / wanli256 は 3 回のまま。

## 追記 (2026-09-22 14:37Z) — ユーザー指示で 5090 に戻す (Mac は中断)
「前は動いた」(同じ 5090 で 07-28 に vllm 0.22.1rc1.dev357 で NVFP4 が動作)。Mac の測定は typesafe102 の 90/102 で中断 (authored144 / wanli256 の 1 回目は保持・out/ に退避)。
5090 の 3 回目: MoE カーネルを FlashInfer CUTLASS から MARLIN に切り替え、KV キャッシュの fp8 も外す (`OPENJEV_VLLM_ARGS`)。閾値・問題セット・変換は変更しない。成功したら Mac の数字とは混ぜず 5090 で全部測り直す。

## 変更履歴 追記 (2026-09-25 09:30Z・再開前・新しい測定は未実施) — Mac MLX で再開
この節は 14:37Z の追記 (5090 に戻す) を**置き換える**。以後の測定はすべて Mac M1 Pro 32GB・MLX で行う。
- 5090 経路は放棄。14:36:26Z の 7 回目 (MARLIN・KV fp8 なし) も 14:39:32Z (23:39 JST) に同じ bugcheck 0x00020001 で PC が落ちていた (System イベント 41/1001 で確認。09-22 の記録には結果が無かった)。**ブルースクリーンは計 3 回** (12:33Z / 12:59Z / 14:39Z)。5090 経路の数字は無い
- 環境は 09-22 と同一を確認: openjev e04794a・mlx 0.32.2・mlx-vlm 0.6.15・macOS 27.0 (26A428)。重みは既定 HF キャッシュに残っていた (du が symlink を辿らず 264KB に見えただけ。再取得しない)。起動コマンドは同じ `OPENJEV_BACKEND=mlx python -m openjev` (repo 直下)。予期しない再取得を防ぐため `HF_HUB_OFFLINE=1` だけ足す (モデルの挙動には関係しない環境変数)
- 問題セット・run_d2.py / run_d3_gen.py / run_d3_load.py・設問文・変換は変更しない (sha256 は FROZEN.sha256)
- **typesafe102 は 3 回に戻す** (14:05Z の「1 回だけ」を取り消す)。1 回目の途中 90/102 (out/d2-typesafe102-r1-partial90.jsonl) は記録として残すが採点に使わない (一度も採点していない・eval ファイルなし)。1 回目から全行やり直す
- authored144 / wanli256 の 1 回目 (09-22) は同じ commit・重み・設定・スクリプトなので 3 回のうち 1 回として使う。2・3 回目を今回足す
- 実行順: authored/wanli の 2・3 回目 → 読み vs 生成 → 同時数 → typesafe102 ×3 (閾値のある項目を先に終える)
- D3 読み vs 生成: 交互の回数を **5 回** に増やす (PREREG は 3 回)。ただし生成 1 周 (144 問) が 15 分を超える場合は PREREG どおり 3 回。合格線 3 倍は変えない。判定値は 5 (または 3) 回の全体時間の中央値の比。平均 ± SE も併記
- D3 同時数: 同時 1 と 16 (README の MLX 記述と比べられる点) は 200 リクエストを **5 回** (seed 1〜5)、32 / 64 は 1 回。各回の前に 8 リクエストのウォームアップ (スクリプト内蔵)。比較先は README の M4 Max 記述 (0.39 秒/3 問・16 同時で約 4 req/s)。RTX PRO 6000 表は機械が違う参考値としてだけ書く。MLX は読みを 1 本ずつ処理するので 16/32/64 で req/s が横ばい・p95 が同時数に比例するのは想定どおり
- typesafe102 の追加指標 (PREREG に無かったもの・結果を見る前に定義):
  - 本物 Jev との一致: DiffusionGemma の argmax と `published_models.typesafe.distribution` の argmax の一致率 (行単位・二項 SE、ケース均等も併記) と、Jev 分布との TV 距離
  - 校正 (探索的・判定に使わない): 正解 = row.label。多クラス Brier (one-hot との二乗誤差の和) と ECE (top-1 確信度・幅 0.1 の等幅 10 ビン)。DiffusionGemma・本物 Jev・前回 Qwen 版 (予測が残っていれば) で同じ式
- 採点の 2 ルート目: evaluate.py とは別に mean_family_balanced_accuracy を独立に書き直した集計で再計算し、浮動小数の精度で一致させる (09-22 の「突合」は素の一致率という別の量だった)。素の argmax 一致率も併記
- 読み直しの乱数は固定 seed のため 3 回が同じになりうる。その場合 3 回の SE は 0 になるので、行単位の二項 SE / bootstrap を併記する。前回 Qwen 版との対比較は evaluate.py --comparison を回ごとに実行して報告
- Mac の取り合い: `~/MAC.lock` を取ってから重い作業をする。nemo-speech など他の重い処理が動いている間・空きメモリが 16GB を大きく下回る間は起動・測定しない。D3 の各区間の前にも確認する

## 変更履歴 追記 (2026-09-26 05:50Z・D3 同時数 seed 5 の途中で発覚) — Mac がスリープを繰り返していた
- 発覚: `pmset -g log` で 2026-09-25 以前から測定中ずっと「Maintenance Sleep」と DarkWake を繰り返していた (1 時間あたり 5〜84 回)。ssh で接続した間だけ起きて処理が進み、切れると数十秒で寝る。各段の間に 1〜2 時間の空きがあったのはこのため。**測定側の見落とし** (caffeinate を付けずに nohup で起動した)
- 影響の見立て: D2 の精度 (2 セット × 3 回) と typesafe102 は値に影響しない (寝ている間は止まるだけ)。D3 の時間 (読み vs 生成 r1〜r5・同時数 seed 1〜4) は `time.perf_counter` (mach_absolute_time) がスリープ中に進まないため wall_s にスリープ時間は入らない。ただし処理途中で凍結→復帰が挟まった可能性は否定できない。反復間の wall_s は 194〜207 秒 (生成) / 193〜204 秒 (読み) で安定しているので、大きな汚染は見えない
- 対処: 05:50Z に `caffeinate -i -s -w <runner pid>` を付けた。以後の段 (seed 5・同時 32/64・typesafe102 × 3) は寝ない状態で測る
- 事後の確認 (post_hoc・判定には使わない): 完走後、時間が許せば読み vs 生成を 1 回と同時数 1/16 を 1 seed、寝ない状態で追加で測り、上の反復と同じ範囲に入るかを RESULTS に併記する
- RESULTS には「D3 の時間は Mac が断続的にスリープしていた状態で測った」と明記する。動画に入れる場合も同じ

## 変更履歴 追記 (2026-09-26 07:27Z・本測定の回収後・事後確認の前) — 事後確認の「同じ範囲」の定義と区間の訂正
- 本測定の結果 (D3 を含む) は回収済み。事後確認 (post_hoc) はまだ測っていない。この節は事後確認の数字を見る前に書く
- 事後確認の手順: `~/MAC.lock` を取り、`caffeinate -i -s` をサーバ起動前から終了まで掛けたまま、同じ commit・重み・起動コマンドでサーバを起動。数えないウォームアップ (読み 3 問・生成 3 問) の後、読み vs 生成 1 回 (authored144・読み→生成の順) と `run_d3_load.py --levels 1,16 --n 200 --seed 7`。出力は out/posthoc-nosleep/。期間中の `pmset -g log` を回収し、Sleep / DarkWake が 0 件であることを確かめる
- 「同じ範囲」の定義: (1) 読み/生成の比 (全体時間) が本測定 5 回の最小〜最大に入る (2) 同時 1・16 の req/s と p50 が本測定 seed 1〜5 の最小〜最大に入る。外れた場合は外れた量を書く。事後確認の値は判定に使わない
- 区間の訂正: 05:50Z の追記は「以後の段 (seed 5・…)」と書いたが、times-0925.txt では seed 5 は 05:49:42Z に終わっており caffeinate より前。caffeinate なしで測ったのは D2 authored/wanli の 2・3 回目・読み vs 生成 r1〜r5・同時数 seed 1〜5。caffeinate ありは同時 32/64 と typesafe102 × 3 だけ
