# qwen38-flash-next-iq1m-cluster — 保留 (採点なし) / On hold (not scored)

- モデル / Model: `Qwen3.8-Flash-Next-UD-IQ1_M`
- 実行日 / Attempted on: 2026-08-27

**理由 / Reason**: thinking ON で実行 (シリーズの凍結条件 think:false と異なる)。A1・C2 は思考が max_tokens 4096 を使い切り本文0文字で、その tok/s は割り算で生まれた無効値。正式な採点は --reasoning off の qwen38-flash-next-iq1m-cluster-nothink を参照

これは環境側の非互換であって、モデルの成績ではありません。**この回の数値は実測値として扱えません**
(出力0文字を割った tok/s のような無効値を含みます)。ランタイムが対応してから同じ条件で測り直します。
This is a runtime incompatibility, not a model result. **Numbers from this run are not valid measurements**
(they include values derived from zero-length output). It will be re-run once the runtime supports the architecture.

## 生ログ / Raw logs

- [`A1.md`](./A1.md)
- [`A2.md`](./A2.md)
- [`B1.md`](./B1.md)
- [`B2.md`](./B2.md)
- [`C1.md`](./C1.md)
- [`C2.md`](./C2.md)
- [`_summary.json`](./_summary.json)
