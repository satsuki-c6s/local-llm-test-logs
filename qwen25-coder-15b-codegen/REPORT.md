# qwen25-coder-15b-codegen — 実測ログ / Measured Log

- モデル / Model: `qwen2.5-coder:1.5b (Ollama, Q4_K_M 1GB, RTX 5090 単機)`
- 測定日 / Measured on: 2026-08-08
- シリーズ / Series: codegen (実アプリ3課題の一発生成)

## 実行条件 / Run Conditions

| 項目 / Item | 値 / Value |
|---|---|
| ランタイム・構成 / Runtime | 上のモデル名に併記 / stated in the model name above |
| モデル digest / Model digest | — (この回は未記録 / not recorded) |
| 生成パラメータ / Generation params | この回は記録していません / not recorded for this run |
| 縛り / Constraints | 単一HTML・外部ライブラリとCDN禁止 / single HTML, no external libs or CDNs |
| 試行回数 / Attempts | 各問1件の記録 / one record per task |
| 測定日 / Measured on | 2026-08-08 |

## 3課題の実測 / Measurements (3 tasks)

| 課題 / Task | 内容 / Label | tok/s | 所要秒 / Seconds | HTML行数 / HTML lines | 終了理由 / Finish |
|---|---|---|---|---|---|
| T1 | ToDoアプリ | 443 | 10 | 191 | stop |
| T2 | ブロック崩し | 432.7 | 3 | 141 | stop |
| T3 | 軌道シミュレーター | 428.5 | 3 | 97 | stop |

一発勝負・単一HTMLファイル縛り・外部ライブラリとCDN禁止で生成させた3課題です。
Three tasks generated in a single shot, as one standalone HTML file, with no external libraries or CDNs.

## 再現方法 / Reproducing this run

この回は digest を記録していないため、コマンドで固定できる再現手順がありません。
実行時の構成は上のモデル名と実行条件の表がすべてです。
This run has no recorded digest, so there is no command that pins it. The model name and the run-conditions table above are the full record.

## 生ログ / Raw logs

- [`T1.html`](./T1.html)
- [`T1.md`](./T1.md)
- [`T2.html`](./T2.html)
- [`T2.md`](./T2.md)
- [`T3.html`](./T3.html)
- [`T3.md`](./T3.md)
- [`_summary.json`](./_summary.json)

---

動画リンクは別途 model-map から付与する (未実装) / Video link to be added from the model map (not yet implemented).
