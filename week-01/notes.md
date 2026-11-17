# Week 1 Notes

## Day 1
- pwd: shows which folder I am in
- ls: lists what is inside the folder
- whoami: shows which user I am (gaju)
- Set up WSL2, Ubuntu and Docker. hello-world ran successfully.
### Filesystem and permissions

### Commands learned
| Command | What it does | My example |
|---|---|---|
| pwd | shows the current folder | /home/gaju/lab |
| ls -la | lists everything with details, including hidden files | ls -la ~ |
| cd, mkdir -p | move into a folder, create folders (and parents) | mkdir -p ~/lab/{data,logs,scripts} |
| cp, mv, rm | copy, move/rename, delete (no recycle bin) | cp data/a.txt data/b.txt |
| find | search by name | find ~ -name "notes.md" |
| chmod | change permissions | chmod +x script.sh |
| chown | change owner (needs sudo) | sudo chown gaju:gaju file |

### Linux folder map
- /home: user files | /etc: configs | /var/log: logs | /tmp: temporary files | /opt: extra software
- /mnt/c is Windows C:. Keep projects in the Linux home, not there (slow, odd permissions).

### Reading permissions
- ls -l output: first character is the type (d folder, - file), then three trios: owner, group, others.
- r = read (4), w = write (2), x = execute (1). On folders, x means I can enter it.
- 644 = rw-r--r-- (owner edits, others read). 755 = rwxr-xr-x (scripts, folders). 640 = rw-r----- (group reads, others nothing). 600 = only me.
- Scripts need chmod +x before they can run. "Permission denied" is the first error to check.
- umask sets default permissions for new files (022 gives files 644, folders 755).

### Mistakes and errors
| What I typed | Error | Cause | Fix |
|---|---|---|---|
| git status in Windows Git Bash | thousands of untracked files | old .git in C:\Users\HP | work only in Ubuntu repo ~/data-engineering-journey |
| git remote add origin | Read-only file system | WSL disk went read-only | wsl --shutdown in PowerShell, reopen Ubuntu |
| find ~ -name notes.md | no output | file was never saved in nano | Ctrl+O, Enter, then Ctrl+X |

### Questions I still have
-
