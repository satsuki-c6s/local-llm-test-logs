# qwen38-flash-next-iq1m-single212 — 実測ログ / Measured Log

- モデル / Model: `Qwen3.8-Flash-Next-UD-IQ1_M`
- 測定日 / Measured on: 2026-08-27

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム / Runtime | `llama.cpp-rpc` |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| top_p | 0.9 |
| temperature / seed | 指定不可 (ランタイムが未サポート) / not settable (unsupported by the runtime) |
| max_tokens / context | 4096 / 8192 |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-08-27 |

> **この回は他の回と同じ土俵ではありません / Not on the same footing as other runs**
> - 5台RPCクラスターではなく単機 (212, VRAM32GB+RAM64GB=96GB) の参考実行。正式採点はクラスター (qwen38-flash-next-iq1m-cluster-nothink) を正とする
> - バックエンドが違う (単機 CUDA+CPU vs RPC分散) ため tok/s を並べて比較しない。単機は約8倍速いが同一条件ではない
> - 採点も◎3 △1 ×2 でクラスター側 (◎3 ○2 ×1) と異なる — 出力そのものが変わる

## 6問の実測 / Measurements (6 tasks)

| 問題 / Task | tok/s | 出力文字数 / Output chars |
|---|---|---|
| A1 | 22.2 | 2792 |
| A2 | 11.9 | 157 |
| B1 | 23.1 | 911 |
| B2 | 19.4 | 226 |
| C1 | 24.2 | 2438 |
| C2 | 14.2 | 46 |

tok/s は1リクエストの初期化コストを含むため、**問題間で順位を比較しないでください**。短い出力ほど低く出ます。
Each tok/s includes per-request startup cost, so **do not rank tasks against each other**; shorter outputs read lower.

## 再現方法 / Reproducing this run

この回は digest を記録していないため、コマンドで固定できる再現手順がありません。
実行時の構成は上のモデル名と実行条件の表がすべてです。
This run has no recorded digest, so there is no command that pins it. The model name and the run-conditions table above are the full record.

## 生ログ / Raw logs

- [`A1.md`](./A1.md)
- [`A2.md`](./A2.md)
- [`B1.md`](./B1.md)
- [`B2.md`](./B2.md)
- [`C1.md`](./C1.md)
- [`C2.md`](./C2.md)
- [`_summary.json`](./_summary.json)

---

動画リンクは別途 model-map から付与する (未実装) / Video link to be added from the model map (not yet implemented).
