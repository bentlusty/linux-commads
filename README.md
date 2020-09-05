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

## Directory Navigation
### Change to /home directory
```bash
$ cd /home
```

### Change to the previous directory
```bash
$ cd -
```

### Go up one level of the directory tree
```bash
$ cd ..
```
### Print’s current directory you are in
```bash
$ pwd
```

## System Information
### Display Linux kernel information
```bash
$ uname -a
```

### Display kernel release information
```bash
$ uname -r
```

### Show how long the system has been running + load
```bash
$ uptime
```

### Show system hostname
```bash
$ hostname
```

### Display the IP addresses of the host
```bash
$ hostname -I
```

### Show system reboot history
```bash
$ last reboot
```

### Show the current date and time
```bash
$ date
```

### Show this month’s calendar
```bash
$ cal
```

### Display who is online
```bash
$ w
```

### Who you are logged in as
```bash
$ whoami
$ id
```

## Hardware Information
###Display CPU information

```bash
$ cat /proc/cpuinfo
```

### Display number of CPU cores
```bash
$ nproc
```

### Display memory information
```bash
$ cat /proc/meminfo
```

### Display environment variables of a process, e.g: PID 1
```bash
$ cat /proc/1/environ
```

### Display free and used memory ( -h for human-readable, -m for MB, -g for GB.)
```bash
$ free -h
```

##System Monitoring, Statistics, Debugging
### Display and manage the running processes
```bash
$ top
```

###Install and use a friendly interactive process viewer (alternative to top)
```bsah
$ apt install htop
$ htop
```

### Display processor related statistics (refresh every 1 second)
```bash
$ mpstat 1
```

### Display virtual memory statistics (refresh every 1 second)
```bash
$ vmstat 1
```

### Display disk I/O statistics (refresh every 1 second)
```bash
$ iostat 1
```

### List all open files on the system
```bash
$ lsof
```

### List files opened by the user (e.g: root)
```bash
$ lsof -u USER
```

###List files opened by a certain process with PID (e.g: 1)
```bash
$ lsof -p PIS
```

### Display disk space occupied by current directory ( -h for human-readable, -s summarize)
```bash
$ du -sh
```

### Execute “df -h”, showing periodic updates every 1 second (pro tip: -d flag shows visual updates)
```bash
$ watch -n1 df -h
```

## File and Directory
### List all files (including hidden) in a long listing human-readable format in the current directory (specifying . is optional).
```bsah
$ ls -hal
```

###Display the present working directory
```bash
$ pwd
```
### Create one or more new empty file
```bash
$ touch file1 file2
```

### Create new directory
```bash
$ mkdir dir1
```

### Create a directory tree using -p option
```bash
$ mkdir -p dir1/dir2/dir3
```

### List the directory tree using tree command
```bash
$ tree dir1
```
### Copy (duplicate) file(s) from one directory to another (-v option for enabling verbose mode)
```bash
$ cp -v file1 dir1/file1-copy
```
### Copy directory and all it’s content to a new directory
```bash
$ cp -vr dir1 dir1-copy
```

### Rename or move a file. If file2 is a directory, then file1 into moved into that directory
```bash
$ mv -v file1 file1-rename
$ mv -v file1-rename dir1
```

### Remove a file or empty directory (-f option force deletes without asking)
```bash
$ rm file1
```

### Remove a directory and its contents recursively (-v option for enabling verbose mode)
```bash
$ rm -vr dir1
```

### Create a symbolic link (pointer) to a file or directory
```bash
$ ln -s file1 file1-link
```

### Write a simple text to a file
```bash
$ echo "hello, world!" > hello.txt
```

### View the contents of a file
```bash
$ cat hello.txt
```

### Paginate through a large file
```bash
$ less hello.txt
```

### Display the first 20 lines of a file
```bash
$ head -n 20 hello.txt
```

### Display the last 20 lines of a file
```bash
$ tail -n 20 hello.txt
```

### Display the last 10 lines of a file and follow the file as it updated.
```bash
$ tail -f hello.txt
```

## Process Management
A *process* is a running instance of a program.
### Display your currently running processes
```bash
$ ps
```

### Display every process on the system.
```bash
$ ps auxf
```

### Display process information for the process name
```bash
$ ps uf -C processname
```

### Display interactive real-time view of running processes
```bash
$ top
$ htop
```

### Look-up process ID based on a name
```bash
$ pgrep nginx
```

### Kill a process with a given process ID. By default TERM signal is sent
```bash
$ kill PID
```

### Send a custom signal to a process with given process ID
```bash
$ kill -s SIGNAL_NUMBER pid
```

### List all available signals
```bash
$ kill -l
```

### Kill a process based on a name
```bash
$ pkill nginx
```

### Run a command as a background job
```bash
$ (sleep 30; echo "woke up after 30 seconds") &
```

### List background jobs
```bash
$ jobs
```

### Display stopped or background jobs
```bash
$ bg
```

### Brings the most recent background job to the foreground
```bash
$ fg
```

### Brings job N to the foreground
```bash
$ fg N
```

### Kill job N
```bash
$ kill %N
```

## File Permissions
### Give all permission to the owner, read execute to the group and nothing to others
```bash
# Create a file
$ touch file1

# Set permission using either of the method
$ chmod 750 file1
$ chmod u=rwx,g=rx,o= file1

# List the file permission
$ ls -lh file1
```

### Change ownership of a file or directory to a given user and group
```bash
$ chown user:group file1
```

