### toolCall exec
```json
{
 "command": "cd /workspace && ls -la",
 "pty": false
}
```

### toolResult exec (error)
```
発生場所 行:1 文字:15
+ cd /workspace && ls -la
+               ~~
トークン '&&' は、このバージョンでは有効なステートメント区切りではありません。
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : InvalidEndOfLine

(Command exited with code 1)
```
