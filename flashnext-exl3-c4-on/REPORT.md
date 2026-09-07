# flashnext-exl3-c4-on — 保留 (採点なし) / On hold (not scored)

- モデル / Model: `flashnext-exl3-3.05bpw`
- 実行日 / Attempted on: 2026-09-03

**理由 / Reason**: 出力0文字の問題が 1 件あり、その tok/s は割り算で生まれた無効値です (実測値ではありません)

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
