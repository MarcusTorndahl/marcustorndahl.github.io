# marcustorndahl.github.io

The scope of this blog is to primarily focus on software development.

## Linux

Find current working directory of a running process
```bash
$ pwdx <PID>

$ lsof -p <PID> | grep cwd

$ readlink -e /proc/<PID>/cwd
```

## WSL - Windows Subsystem for Linux

Find WSL directory from Windows Explorer
```cmd
$ dir \\wsl$\<distribution>
```

Open up the Windows Explorer with the current directory from WSL terminal
```bash
$ explorer.exe .
```

Change directory to host root dircetory from WSL terminal
```bash
$ cd /mnt/c
```


## Git
Aliases (or shortcuts) make the git-experience much more efficient and fun:
```ini
[alias]
    st = status
    br = branch --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(contents:subject) %(color:green)(%(committerdate:relative)) [%(authorname)]' --sort=-committerdate
    ca = commit --amend
    co = checkout
    com = checkout master
    cb = checkout -b
    l = log --decorate
    ll = log --pretty='format:%h %G? %aN %s'
    ls = log --stat --summary
    last = log --decorate -1 HEAD
    lg = log --oneline --decorate --all --graph
    lg1 = log --graph --abbrev-commit --all --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)'
    lg2 = log --graph --abbrev-commit --all --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
    lg3 = log --graph --abbrev-commit --all --pretty=format:'%C(red)%h%C(reset) -%C(yellow)%d%C(reset) %s %C(green)(%cr) %C(bold blue)<%an>%C(reset)'
    lg4 = log --graph --abbrev-commit --all --pretty=format:'%C(red)%h%C(reset) %C(green)(%ci)%C(reset) -%C(yellow)%d%C(reset) %s %C(bold blue)<%an>%C(reset)'
    lg5 = log --graph --abbrev-commit --all --pretty=format:'%C(red)%h%C(reset) %C(green)(%ci)%C(reset) -%C(yellow)%d%C(reset) %s %C(bold blue)<%an - %ae>%C(reset)'
    lg6 = log --graph --abbrev-commit --first-parent master --pretty=format:\"%C(red)%h%C(reset) %C(green)(%ci)%C(reset) %C(yellow)%d%C(reset) %C(bold blue)<%ae>%C(reset)\"

    slg = shortlog -sne --after='$(date +%Y)-01-01'

    root = rev-parse --show-toplevel
    wdiff = diff --color-words="[^[:space:]]|([[:alnum:]]|UTF_8_GUARD)+"
```

