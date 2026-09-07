あなたは Windows 11 上で動いています。exec ツールのシェルは PowerShell です。作業ディレクトリは
ワークスペース直下の project フォルダです。作業が終わったら、何をしたかを3行以内で報告してください。

project フォルダにある小さな Node.js プロジェクトを調べて、次のスキーマの JSON を project/report.json に
書き出してください。値はファイルの中身から読み取ってください。推測で埋めないでください。
{
  "project": 文字列 (package.json の name),
  "version": 文字列 (package.json の version),
  "port": 数値 (サーバーが実際に待ち受けるポート番号),
  "database_file": 文字列 (データベースファイルのパス),
  "entrypoint": 文字列 (package.json の main),
  "dependencies": 文字列の配列 (dependencies のパッケージ名のみ。アルファベット順。devDependencies は含めない),
  "latest_release": { "version": 文字列, "date": "YYYY-MM-DD" } (CHANGELOG の最新リリース),
  "todo_count": 数値 (src フォルダ内の .js ファイルで「TODO」を含むコメント行の合計数)
}
