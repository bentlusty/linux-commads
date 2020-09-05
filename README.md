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
apt update
```

Upgrade packages in bulk
```bash
apt
```
Search for a package named htop
```bash
apt search htop
```

Show information about a package
```bash
apt show htop
```

Install a package named htop
```bash
apt install htop
```

Remove a package named htop
```bash
apt remove htop
```

Install multiple packages
```bash
apt install htop less
```

### apt-file
apt-file is a program to search for packages containing files. Very helpful if you do not remember the name of the package, but you know the command.

Install apt-file using apt
```bash
apt install apt-file
```

Update the apt-file cache
```bash
apt-file update
```

Search for a package that provides postgres command
```bash
apt-file search bin/psql
```

## Directory Navigation
### Change to /home directory
```bash
cd /home
```

### Change to the previous directory
```bash
cd -
```

### Go up one level of the directory tree
```bash
cd ..
```
### Print’s current directory you are in
```bash
pwd
```

## System Information
### Display Linux kernel information
```bash
uname -a
```

### Display kernel release information
```bash
uname -r
```

### Show how long the system has been running + load
```bash
uptime
```

### Show system hostname
```bash
hostname
```

### Display the IP addresses of the host
```bash
hostname -I
```

### Show system reboot history
```bash
last reboot
```

### Show the current date and time
```bash
date
```

### Show this month’s calendar
```bash
cal
```

### Display who is online
```bash
w
```

### Who you are logged in as
```bash
whoami
id
```

## Hardware Information
###Display CPU information

```bash
cat /proc/cpuinfo
```

### Display number of CPU cores
```bash
nproc
```

### Display memory information
```bash
cat /proc/meminfo
```

### Display environment variables of a process, e.g: PID 1
```bash
cat /proc/1/environ
```

### Display free and used memory ( -h for human-readable, -m for MB, -g for GB.)
```bash
free -h
```

##System Monitoring, Statistics, Debugging
### Display and manage the running processes
```bash
top
```

###Install and use a friendly interactive process viewer (alternative to top)
```bsah
apt install htop
htop
```

### Display processor related statistics (refresh every 1 second)
```bash
mpstat 1
```

### Display virtual memory statistics (refresh every 1 second)
```bash
vmstat 1
```

### Display disk I/O statistics (refresh every 1 second)
```bash
iostat 1
```

### List all open files on the system
```bash
lsof
```

### List files opened by the user (e.g: root)
```bash
lsof -u USER
```

###List files opened by a certain process with PID (e.g: 1)
```bash
lsof -p PIS
```

### Display disk space occupied by current directory ( -h for human-readable, -s summarize)
```bash
du -sh
```

### Execute “df -h”, showing periodic updates every 1 second (pro tip: -d flag shows visual updates)
```bash
watch -n1 df -h
```

## File and Directory
### List all files (including hidden) in a long listing human-readable format in the current directory (specifying . is optional).
```bsah
ls -hal
```

###Display the present working directory
```bash
pwd
```
### Create one or more new empty file
```bash
touch file1 file2
```

### Create new directory
```bash
mkdir dir1
```

### Create a directory tree using -p option
```bash
mkdir -p dir1/dir2/dir3
```

### List the directory tree using tree command
```bash
tree dir1
```
### Copy (duplicate) file(s) from one directory to another (-v option for enabling verbose mode)
```bash
cp -v file1 dir1/file1-copy
```
### Copy directory and all it’s content to a new directory
```bash
cp -vr dir1 dir1-copy
```

### Rename or move a file. If file2 is a directory, then file1 into moved into that directory
```bash
mv -v file1 file1-rename
mv -v file1-rename dir1
```

### Remove a file or empty directory (-f option force deletes without asking)
```bash
rm file1
```

### Remove a directory and its contents recursively (-v option for enabling verbose mode)
```bash
rm -vr dir1
```

### Create a symbolic link (pointer) to a file or directory
```bash
ln -s file1 file1-link
```

### Write a simple text to a file
```bash
echo "hello, world!" > hello.txt
```

### View the contents of a file
```bash
cat hello.txt
```

### Paginate through a large file
```bash
less hello.txt
```

### Display the first 20 lines of a file
```bash
head -n 20 hello.txt
```

### Display the last 20 lines of a file
```bash
tail -n 20 hello.txt
```

### Display the last 10 lines of a file and follow the file as it updated.
```bash
tail -f hello.txt
```

## Process Management
A *process* is a running instance of a program.
### Display your currently running processes
```bash
ps
```

### Display every process on the system.
```bash
ps auxf
```

### Display process information for the process name
```bash
ps uf -C processname
```

### Display interactive real-time view of running processes
```bash
top
htop
```

### Look-up process ID based on a name
```bash
pgrep nginx
```

### Kill a process with a given process ID. By default TERM signal is sent
```bash
kill PID
```

### Send a custom signal to a process with given process ID
```bash
kill -s SIGNAL_NUMBER pid
```

### List all available signals
```bash
kill -l
```

### Kill a process based on a name
```bash
pkill nginx
```

### Run a command as a background job
```bash
(sleep 30; echo "woke up after 30 seconds") &
```

### List background jobs
```bash
jobs
```

### Display stopped or background jobs
```bash
bg
```

### Brings the most recent background job to the foreground
```bash
fg
```

### Brings job N to the foreground
```bash
fg N
```

### Kill job N
```bash
kill %N
```

## File Permissions
### Give all permission to the owner, read execute to the group and nothing to others
```bash
# Create a file
touch file1

# Set permission using either of the method
chmod 750 file1
chmod u=rwx,g=rx,o= file1

# List the file permission
ls -lh file1
```

### Change ownership of a file or directory to a given user and group
```bash
chown user:group file1
```

## Networking
### Display information of all available network interfaces
```bash
ip addr
```

### Display information of eth0 interface
```bash
ip addr show eth0
```

### Display IP routing table
```bash
ip route
```

### Ping a hostname or IP address
```bash
ping google.com
ping 8.8.8.8
```

### Display registration information of a domain
```bash
whois medium.com
```

### DNS lookup a domain
```bash
dig medium.com A     # IPv4 addresses
dig medium.com AAAA  # IPv6 addresses
dig medium.com NX    # Nameservers

host medium.com     # IPv4 addresse
```

### Display hostname and IP address of the local machine
```bash
hostname
hostname -i
```

### Download files from a remote HTTP server
```bash
wget [http://ipv4.download.thinkbroadband.com/5MB.zip](http://ipv4.download.thinkbroadband.com/5MB.zip)
curl --output 5MB.zip [http://ipv4.download.thinkbroadband.com/5MB.zip](http://ipv4.download.thinkbroadband.com/5MB.zip)
```

### Display all process listening on TCP or UDP ports
```bash
netstat -plunt
lsof -i
lsof -i tcp     # only TCP ports
```

## Text Search
### Search for a pattern in a text file
```bash
grep pattern file

# For example:
grep root /etc/passwd
```

### Search recursively for a pattern in a text file inside a directory
```bash
grep -R "/bin/bash" /etc
```

### Search for pattern and output N lines before (B) or after (A) pattern match
```bash
grep -B 5 root /etc/passwd
grep -A 3 root /etc/passwd
```

### Find files within a directory with a matching filename
```bash
find /etc -iname 'passwd'
find /etc -iname 'pass*'  # glob pattern
```

###Find files based on filesize
```bash
find / -size +1M #  larger than 1MB
find / -size -1M # smaller than 1MB
```

##Disk Usage
### Show free and used space of disk storages

```bash
df -h
```

### Show disk space consumed by a directory or file
```bash
du -sh /var/log
du -h 5MB.zip
```

### Interactive disk usage explorer
```bash
ncdu
```

## Pipes and Redirection
### **REDIRECTION**
### Redirect normal output (stdout) from a command to a file
```bash
echo "hello" > hello.stdout.txt
echo "world" > hello.stdout.txt
```

### Redirect error output (stderr) from a command to a file
```bash
cat somefile 2> cat.stderr.txt
```

### Redirect both normal and error output from a command to a file. Useful for logging.
```bash
ps auxf >& processes.txt
```

### Append normal output (stdout) from a command to a file unlike > which overwrites the file
```bash
echo "hello" >> hello2.stdout.txt
echo "world!" >> hello2.stdout.txt
```

### Append error output (stderr) from a command to a file
```bash
cat some-unknown-file 2>> cat2.stderr.txt
```

### Append both normal and error output (stderr) from a command to a file
```bash
ps auxf &>> processes.txt
```

### **PIPES**
The shell pipe **is a way to **communicate between commands.
### Create a dummy file to learn to pipe
```bash
mkdir pipes-example
cd pipes-example
touch {1..10}.txt
```

### Example 1: Let’s use sort command
```bash
ls -1 *.txt | sort -n    # sorts the output in ASC order
ls -1 *.txt | sort -nr   # sorts the output in DESC order
```

### Example 2: Let’s use head & tail command
```bash
ls -1 *.txt | sort -n | head -n 5  # show the first 5 lines
ls -1 *.txt | sort -n | tail -n 5  # show the last 5 lines
```

### Example 3: Search for a pattern in a text file
```bash
cat /etc/passwd | grep root    # show lines containing string 'root'
```

## Environment Variables
### List all environment variables
```bash
env
```

### Display value of an environment variable
```bash
echo $HOME
echo $SHELL
```

### Create an environment variable
```bash
export PORT=80
export PLATFORM=medium.com
```

### Delete an environment variable
```bash
unset PORT
```

### PATH is one of the common and important environment variables. What do you think will happen if you unset it?
```bash
echo $PATH
unset PATH
```
