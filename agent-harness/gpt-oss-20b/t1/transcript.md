### toolCall read
```json
{
 "path": "project",
 "depth": 3,
 "limit": 200
}
```

### toolResult read (error)
```
{
  "status": "error",
  "tool": "read",
  "error": "EISDIR: illegal operation on a directory, read"
}
```

### toolCall exec
```json
{
 "ask": "dir project",
 "background": false,
 "command": "dir project",
 "elevated": false,
 "env": {},
 "host": "auto",
 "node": "",
 "pty": true,
 "security": "default",
 "timeout": 10,
 "workdir": ""
}
```

### toolResult exec (error)
```
workdir "" is unavailable or not a directory: command was not executed. workdir is treated as a literal path; shell expansions such as "~" are not applied. Use an existing directory, omit an explicit workdir to use the default cwd, or update the configured default cwd.
```

### toolCall exec
```json
{
 "ask": "dir project",
 "background": false,
 "command": "dir project",
 "elevated": false,
 "env": {},
 "host": "auto",
 "node": "",
 "pty": true,
 "security": "default",
 "timeout": 10,
 "workdir": "<runDir>\\workspace"
}
```

### toolResult exec
```
ディレクトリ: <runDir>\workspace\projectMode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        2026/08/30     14:36                src
d-----        2026/08/30     14:36                test
-a----        2026/08/28     15:19            216 package.json
-a----        2026/08/28     15:20            363 README.md
```

### toolCall exec
```json
{
 "ask": "node --test",
 "background": false,
 "command": "node --test",
 "elevated": false,
 "env": {},
 "host": "auto",
 "node": "",
 "pty": true,
 "security": "default",
 "timeout": 10,
 "workdir": "<runDir>"
}
```

### toolResult exec (error)
```
workdir "<runDir>" is unavailable or not a directory: command was not executed. workdir is treated as a literal path; shell expansions such as "~" are not applied. Use an existing directory, omit an explicit workdir to use the default cwd, or update the configured default cwd.
```
