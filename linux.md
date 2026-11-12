# Linux cheat sheet

The answers from every Linux quiz on [@mish.builds](https://www.instagram.com/mish.builds/), plus the one line that explains each.

## Files and permissions

| Task | Command | Why |
|---|---|---|
| Make a script executable | `chmod +x deploy.sh` | `+x` adds execute permission. `chown` changes the owner. |
| What does `chmod 755` give others? | read + execute | 7 = rwx for you, 5 = r-x for group and others. |
| Find files over 100 MB | `find /var -size +100M` | `find` walks the tree. `+100M` = larger than 100 MB. |
| Search every file for a word | `grep -r timeout .` | `-r` goes into subfolders. Add `-n` for line numbers. |
| Where config files live | `/etc` | `/etc` holds config. `/var` holds data that changes, like logs. |

## Disk

| Task | Command | Why |
|---|---|---|
| Free space per filesystem | `df -h` | df = disk free. du = what a folder uses. free = memory. |
| Disk 100% full, du finds nothing | `lsof +L1` | A deleted file is still held open. Restart that process to free the space. |

## Processes

| Task | Command | Why |
|---|---|---|
| Top CPU users right now | `top` | Refreshes live. `uptime` only shows load averages. |
| Load 4.0 on 4 cores | about fully busy | Load counts running + waiting tasks. 4 on 4 cores = full. |
| Signal a process can't ignore | `kill -9` (SIGKILL) | The process gets no say. |
| Keep running after logout | `nohup cmd &` | nohup ignores the hangup. `&` puts it in the background. |
| Follow a log | `tail -n 50 -f app.log` | Last 50 lines, then keeps printing new ones. |

## Network

| Task | Command | Why |
|---|---|---|
| What's listening on 8080 | `ss -ltnp` | listening, TCP, numeric ports, process. |
| Names → IPs before DNS | `/etc/hosts` | Checked first by default. `resolv.conf` lists DNS servers. |

## Shell plumbing

| Task | Command | Why |
|---|---|---|
| Every 5 minutes in cron | `*/5 * * * *` | `5 * * * *` runs once an hour, at minute 5. |
| What `2>&1` does | errors go where output goes | 2 = stderr, 1 = stdout. |

More: [Git](git.md) · [SQL](sql.md) · [Bash](bash.md)
