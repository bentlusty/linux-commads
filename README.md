# linux-commads
## Commands
### unminimize
Restores content and packages that are found on a default Ubuntu in order to make it more suitable for interactive and learning use

### tmux
Running multiple shell sessions in a single terminal window.

Basic tmux: 
* Start new tabbed window: Press Ctrl+b, release and then press c
* Start new window horizontally: Press Ctrl+b, release and press "
* Start new window vertically: Press Ctrl+b, release and press %
* Switch between tabbed window: Press Ctrl+b, release and press p or n
* Switch between horizontal or vertical window: Press Ctrl+b, release and then press ;
* Kill a window: Press Ctrl+b, release and then press x
* Rename a tabbed window: Press Ctrl+b, release and then press ,
* Scroll through window console output: Press Ctrl+b, release and then use arrows to move

### Package Manager
apt is a package manager **to manage packages in **Ubuntu Linux.

Update the packages repository
```bash
$ apt update
```

Upgrade packages in bulk
```bash
$ apt
```
Search for a package named htop
```bash
$ apt search htop
```

Show information about a package
```bash
$ apt show htop
```

Install a package named htop
```bash
$ apt install htop
```

Remove a package named htop
```bash
$ apt remove htop
```

Install multiple packages
```bash
$ apt install htop less
```

### apt-file
apt-file is a program to search for packages containing files. Very helpful if you do not remember the name of the package, but you know the command.

Install apt-file using apt
```bash
$ apt install apt-file
```

Update the apt-file cache
```bash
$ apt-file update
```

Search for a package that provides postgres command
```bash
$ apt-file search bin/psql
```


