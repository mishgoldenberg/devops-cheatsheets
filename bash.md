# Bash cheat sheet

The answers from every Bash quiz on [@mish.builds](https://www.instagram.com/mish.builds/), plus the one line that explains each.

## Script basics

| Task | Code | Why |
|---|---|---|
| First line | `#!/bin/bash` | The shebang tells the kernel which interpreter runs it. |
| First argument | `$1` | `$0` is the script name. |
| All arguments, kept separate | `"$@"` | Quoted, arguments with spaces stay intact. |
| Exit code of last command | `echo $?` | `$!` last background PID, `$$` this shell, `$#` arg count. |
| Command output into a variable | `x=$(date)` | No spaces around `=`. |
| Keep `$HOME` literal | `'single quotes'` | Double quotes still expand. |

## Safety switches

| Task | Code | Why |
|---|---|---|
| Stop at the first error | `set -e` | `set -x` only echoes commands. |
| Fail if any pipe step fails | `set -o pipefail` | Otherwise only the last command sets the exit code. |
| Run B only if A worked | `a && b` | `||` runs on failure. |

## Files and output

| Task | Code | Why |
|---|---|---|
| Does the file exist? | `[ -f file ]` | Exists and is a regular file. `-z`/`-n` test strings. |
| Loop over .log files | `for f in *.log; do ...; done` | The shell expands `*.log`. |
| Output + errors to one file | `cmd > out.log 2>&1` | Order matters: redirect stdout first. |

More: [Linux](linux.md) · [Git](git.md) · [SQL](sql.md)
