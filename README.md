# Bash Scripting Cheat Sheet

![Bash-Scripting-Cheat-Sheet](https://socialify.git.ci/king04aman/Bash-Scripting-Cheatsheet/image?description=1&font=Jost&forks=1&issues=1&language=1&logo=https%3A%2F%2Fimages.weserv.nl%2F%3Furl%3Dhttps%3A%2F%2Favatars.githubusercontent.com%2Fu%2F62813940%3Fv%3D4%26h%3D250%26w%3D250%26fit%3Dcover%26mask%3Dcircle%26maxage%3D7d&name=1&owner=1&pattern=Circuit%20Board&pulls&pulls=1&stargazers=1&theme=Dark)

_Welcome to the Bash Scripting Cheat Sheet repository! This project aims to be a comprehensive and beginner-friendly resource for learning and mastering Bash scripting. Whether you're a seasoned developer or just starting with shell scripting, this cheat sheet will serve as a handy reference guide._

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Basic Syntax](#basic-syntax)
- [Variables](#variables)
- [Control Structures](#control-structures)
  - [Boolean Operators](#boolean-operators)
  - [Numeric Operators](#numeric-operators)
  - [String Operators](#string-operators)
  - [If Statements](#if-statements)
  - [Inline If Statements](#inline-if-statements)
  - [While Loops](#while-loops)
  - [For Loops](#for-loops)
  - [Case Statements](#case-statements)
- [Functions](#functions)
- [File Operations](#file-operations)
  - [Check Disk Usage](#check-disk-usage)
  - [Monitor CPU Usage](#monitor-cpu-usage)
  - [Display System Information](#display-system-information)
  - [Backup Files](#backup-files)
  - [Check Network Connectivity](#check-network-connectivity)
  - [Check Available Memory](#check-available-memory)
  - [Monitor Disk Usage of a Specific Directory](#monitor-disk-usage-of-a-specific-directory)
  - [List Running Processes](#list-running-processes)
  - [Display Current Date and Time](#display-current-date-and-time)
  - [Generate Random Password](#generate-random-password)
  - [Check System Load Average](#check-system-load-average)
  - [Monitor Network Traffic](#monitor-network-traffic)
  - [Search for a File](#search-for-a-file)
  - [Display System Users](#display-system-users)
  - [Check System Uptime](#check-system-uptime)
- [Text Processing](#text-processing)
  - [Replace in Files](#replace-in-files)
  - [Symbolic Links](#symbolic-links)
  - [Compressing Files](#compressing-files)
    - [zip](#zip)
    - [gzip](#gzip)
    - [tar -c](#tar--c)
  - [Decompressing Files](#decompressing-files)
    - [unzip](#unzip)
    - [gunzip](#gunzip)
    - [tar -x](#tar--x)
- [Command-Line Arguments](#command-line-arguments)
- [Common Utilities](#common-utilities)
  - [HTTP Requests](#http-requests)
  - [Network Troubleshooting](#network-troubleshooting)
  - [DNS](#dns)
  - [Hardware](#hardware)
  - [Terminal Multiplexers](#terminal-multiplexers)
  - [Secure Shell Protocol (SSH)](#secure-shell-protocol-ssh)
  - [Secure Copy](#secure-copy)
  - [Bash Profile](#bash-profile)
  - [Bash Script](#bash-script)
    - [Variables](#variables)
    - [Environment Variables](#environment-variables)
    - [Functions](#functions)
    - [Exit Codes](#exit-codes)
  - [Conditional Statements](#conditional-statements)
    - [Boolean Operators](#boolean-operators)
    - [Numeric Operators](#numeric-operators)
    - [String Operators](#string-operators)
    - [If Statements](#if-statements)
    - [Inline If Statements](#inline-if-statements)
    - [While Loops](#while-loops)
    - [For Loops](#for-loops)
    - [Case Statements](#case-statements)
- [Input/Ouput Redirectors](#input-output-redirectors)
- [Command Line Processing Cycle](#command-line-processing-cycle)
- [Debugging Script](#debugging-shell-scripts)
- [Colors and Styles](#colors-and-styles)
- [Tips and Tricks](#tips-and-tricks)
- [Shortcut Keys](#shortcut-keys)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Bash (Bourne Again SHell) is a powerful and widely used shell scripting language in the Unix/Linux environment. It provides a command-line interface for interacting with the operating system and automating tasks.

This cheat sheet is designed to help you understand and utilize Bash scripting effectively. It covers essential concepts, syntax, and common patterns, making it an ideal resource for both beginners and experienced developers.

## Getting Started

If you're new to Bash scripting, here are some resources to help you get started:

- [Bash Guide for Beginners](http://tldp.org/LDP/Bash-Beginners-Guide/html/index.html)
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html)
- [Bash Academy](https://guide.bash.academy/)

## Basic Syntax

Learn the fundamental syntax of Bash scripting:

```bash
#!/bin/bash

# Your code here
```

## Variables

Declare and use variables in Bash:

```bash
name="John"
echo "Hello, $name!"
```

## Control Structures

Understand control structures like if statements and loops:

```bash
if [ condition ]; then
  # Code to execute if condition is true
fi

for i in {1..5}; do
  # Code to repeat 5 times
done
```

## Functions

Define and call functions in Bash:

```bash
function greet {
  echo "Hello, $1!"
}

greet "Alice"
```

## File Operations

Perform file-related operations:

```bash
# Check if a file exists
if [ -e "file.txt" ]; then
  # Code to execute if file exists
fi

# Read from a file
content=$(<file.txt)
```

## Text Processing

Manipulate text using powerful tools like `sed` and `awk`:

```bash
# Replace text in a file
sed 's/old/new/g' input.txt > output.txt

# Print specific columns from a CSV
awk -F',' '{print $1, $3}' data.csv
```

## Command-Line Arguments

Handle command-line arguments in your scripts:

```bash
#!/bin/bash

# Access command-line arguments
echo "Script name: $0"
echo "First argument: $1"
```

## Common Utilities

Explore common Bash utilities:

- `grep`: Search for patterns in files.
- `cut`: Extract specific columns from text.
- `find`: Search for files in a directory hierarchy.
- `sort`: Sort lines of text files.

## Command History

```bash
!!                      # Re-run the previous command

touch foo.sh
chmod +x !$             # Apply executable permissions to the last argument of the previous command (foo.sh)
```

## Navigating Directories

```bash
pwd                             # Print the current directory path
ls                              # List directories
ls -a|--all                     # List all directories, including hidden ones
ls -l                           # List directories in long format
ls -l -h|--human-readable       # List directories in long format with human-readable sizes
ls -t                           # List directories by modification time, with newest first
stat foo.txt                    # Display size, creation, and modification timestamps for a file
stat foo                        # Display size, creation, and modification timestamps for a directory
tree                            # Display directory and file tree
tree -a                         # Display directory and file tree, including hidden entries
tree -d                         # Display directory tree
cd foo                          # Change directory to 'foo'
cd                              # Change directory to home directory
cd ~                            # Change directory to home directory
cd -                            # Change directory to the last visited directory
pushd foo                       # Change directory to 'foo' and add the previous directory to the directory stack
popd                            # Return to the directory saved by the last 'pushd' command
```

## Creating Directories

```bash
mkdir foo                                # Create a directory named 'foo'
mkdir foo bar                            # Create multiple directories
mkdir -p|--parents foo/bar               # Create a nested directory
mkdir -p|--parents {foo,bar}/baz         # Create multiple nested directories

mktemp -d|--directory                    # Create a temporary directory
```

## Moving Directories

```bash
cp -R|--recursive foo bar                                       # Copy directory 'foo' to 'bar'
mv foo bar                                                      # Move directory 'foo' to 'bar'

rsync -z|--compress -v|--verbose /foo /bar                      # Copy directory, overwriting destination
rsync -a|--archive -z|--compress -v|--verbose /foo /bar         # Copy directory, without overwriting destination
rsync -avz /foo username@hostname:/bar                          # Copy local directory to remote directory
rsync -avz username@hostname:/foo /bar                          # Copy remote directory to local directory
```

## Deleting Directories

```bash
rmdir foo                               # Delete empty directory 'foo'
rm -r|--recursive foo                   # Delete directory 'foo' and its contents
rm -r|--recursive -f|--force foo        # Delete directory 'foo' and its contents, ignoring nonexistent files and never prompting
```

## Creating Files

```bash
touch foo.txt                           # Create or update file 'foo.txt'
touch foo.txt bar.txt                   # Create multiple files
touch {foo,bar}.txt                     # Create multiple files
touch test{1..3}                        # Create test1, test2, and test3 files
touch test{a..c}                        # Create testa, testb, and testc files

mktemp                                  # Create a temporary file
```

## Standard Output, Standard Error, and Standard Input

```bash
echo "foo" > bar.txt        # Overwrite file 'bar.txt' with content
echo "foo" >> bar.txt       # Append content to file 'bar.txt'

ls exists 1> stdout.txt     # Redirect standard output to a file
ls noexist 2> stderror.txt  # Redirect standard error output to a file
ls 2>&1 > out.txt           # Redirect standard output and error to a file
ls > /dev/null              # Discard standard output and error

read foo                    # Read from standard input and assign to variable 'foo'
```

## Moving Files

```bash
cp foo.txt bar.txt                                 # Copy file 'foo.txt' to 'bar.txt'
mv foo.txt bar.txt                                 # Move file 'foo.txt' to 'bar.txt'

rsync -z|--compress -v|--verbose /foo.txt /bar     # Copy file quickly if it's changed
rsync z|--compress -v|--verbose /foo.txt /bar.txt  # Copy and rename file quickly if it's changed
```

## Deleting Files

```bash
rm foo.txt              # Delete file 'foo.txt'
rm -f|--force foo.txt   # Delete file 'foo.txt', ignore nonexistent files, and never prompt
```

## Reading Files

```bash
cat foo.txt             # Print all contents
less foo.txt            # View contents paginated (g - go to top, SHIFT+g - go to bottom, /foo - search for 'foo')
head foo.txt            # Display top 10 lines of the file
tail foo.txt            # Display bottom 10 lines of the file
open foo.txt            # Open file in the default editor
wc foo.txt              # Count lines, words, and characters in the file
```

## File Permissions

| #   | Permission               | rwx | Binary |
| --- | ------------------------ | --- | ------ |
| 7   | read, write, and execute | rwx | 111    |
| 6   | read and write           | rw- | 110    |
| 5   | read and execute         | r-x | 101    |
| 4   | read only                | r-- | 100    |
| 3   | write and execute        | -wx | 011    |
| 2   | write only               | -w- | 010    |
| 1   | execute only             | --x | 001    |
| 0   | none                     | --- | 000    |

For a directory, execute means you can enter the directory.

| User | Group | Others | Description                                                                                           |
| ---- | ----- | ------ | ----------------------------------------------------------------------------------------------------- |
| 6    | 4     | 4      | User can read and write, everyone else can read (Default file permissions)                            |
| 7    | 5     | 5      | User can read, write, and execute, everyone else can read and execute (Default directory permissions) |

- u - User
- g - Group
- o - Others
- a - All of the above

```bash
ls -l /foo.sh           # List file permissions
chmod +100 foo.sh       # Add execute permission for the user
chmod -100 foo.sh       # Remove execute permission for the user
chmod u+x foo.sh        # Grant execute permission to the user
chmod g+x foo.sh        # Grant execute permission to the group
chmod u-x,g-x foo.sh    # Revoke execute permission from the user and group
chmod u+x,g+x,o+x foo.sh # Grant execute permission to everyone
chmod a+x foo.sh        # Grant execute permission to everyone
chmod +x foo.sh         # Grant execute permission to everyone
```

## Finding Files

Find the binary files for a command.

```bash
type wget                   # Find the binary
which wget                  # Find the binary
whereis wget                # Find the binary, source, and manual page files
```

`locate` uses an index and is fast.

```bash
updatedb                    # Update the index

locate foo.txt              # Find a file
locate --ignore-case foo.txt # Find a file and ignore case
locate f*.txt               # Find text files starting with 'f'
```

`find` doesn't use an index and is slow.

```bash
find /path -name foo.txt                  # Find a file
find /path -iname foo.txt                 # Find a file with case-insensitive search
find /path -name "*.txt"                  # Find all text files
find /path -name foo.txt -delete          # Find a file and delete it
find /path -name "*.png" -exec pngquant {} # Find and execute pngquant on all .png files
find /path -type f -name foo.txt          # Find a file
find /path -type d -name foo              # Find a directory
find /path -type l -name foo.txt          # Find a symbolic link
find /path -type f -mtime +30             # Find files not modified in 30 days
find /path -type f -mtime +30 -delete     # Delete files not modified in 30 days
```

## Find in Files

```bash
grep 'foo' /bar.txt                        # Search for 'foo' in file 'bar.txt'
grep 'foo' /bar -r|--recursive             # Search for 'foo' in directory 'bar'
grep 'foo' /bar -R|--dereference-recursive # Search for 'foo' in directory 'bar' and follow symbolic links
grep 'foo' /bar -l|--files-with-matches    # Show files that match
grep 'foo' /bar -L|--files-without-match   # Show files that don't match
grep 'Foo' /bar -i|--ignore-case           # Case-insensitive search
grep 'foo' /bar -x|--line-regexp           # Match the entire line
grep 'foo' /bar -C|--context 1             # Add N lines of context above and below each search result
grep 'foo' /bar -v|--invert-match          # Show lines that don't match
grep 'foo' /bar -c|--count                 # Count lines that match
grep 'foo' /bar -n|--line-number           # Add line numbers
grep 'foo' /bar --colour                   # Add color to output
grep 'foo\|bar' /baz -R                    # Search for 'foo' or 'bar' in directory 'baz'
grep --extended-regexp|-E 'foo|bar' /baz -R# Use regular expressions
egrep 'foo|bar' /baz -R                    # Use regular expressions
```

### Replace in Files

```bash
sed 's/fox/bear/g' foo.txt               # Replace 'fox' with 'bear' in foo.txt and display to console
sed 's/fox/bear/gi' foo.txt              # Replace 'fox' (case insensitive) with 'bear' in foo.txt and display to console
sed 's/red fox/blue bear/g' foo.txt      # Replace 'red' with 'blue' and 'fox' with 'bear' in foo.txt and display to console
sed 's/fox/bear/g' foo.txt > bar.txt     # Replace 'fox' with 'bear' in foo.txt and save to bar.txt
sed 's/fox/bear/g' foo.txt -i|--in-place # Replace 'fox' with 'bear' in foo.txt and overwrite foo.txt
```

## Symbolic Links

```bash
ln -s|--symbolic foo bar            # Create a symbolic link 'bar' to the 'foo' folder
ln -s|--symbolic -f|--force foo bar # Overwrite an existing symbolic link 'bar'
ls -l                               # Display where symbolic links are pointing
```

## Compressing Files

### zip

Compresses one or more files into \*.zip files.

```bash
zip foo.zip /bar.txt                # Compress bar.txt into foo.zip
zip foo.zip /bar.txt /baz.txt       # Compress bar.txt and baz.txt into foo.zip
zip foo.zip /{bar,baz}.txt          # Compress bar.txt and baz.txt into foo.zip
zip -r|--recurse-paths foo.zip /bar # Compress directory bar into foo.zip
```

### gzip

Compresses a single file into \*.gz files.

```bash
gzip /bar.txt foo.gz           # Compress bar.txt into foo.gz and then delete bar.txt
gzip -k|--keep /bar.txt foo.gz # Compress bar.txt into foo.gz
```

### tar -c

Compresses (optionally) and combines one or more files into a single _.tar, _.tar.gz, _.tpz, or _.tgz file.

```bash
tar -c|--create -z|--gzip -f|--file=foo.tgz /bar.txt /baz.txt # Compress bar.txt and baz.txt into foo.tgz
tar -c|--create -z|--gzip -f|--file=foo.tgz /{bar,baz}.txt    # Compress bar.txt and baz.txt into foo.tgz
tar -c|--create -z|--gzip -f|--file=foo.tgz /bar              # Compress directory bar into foo.tgz
```

## Decompressing Files

### unzip

```bash
unzip foo.zip          # Unzip foo.zip into the current directory
```

### gunzip

```bash
gunzip foo.gz           # Unzip foo.gz into the current directory and delete foo.gz
gunzip -k|--keep foo.gz # Unzip foo.gz into the current directory
```

### tar -x

```bash
tar -x|--extract -z|--gzip -f|--file=foo.tar.gz # Un-compress foo.tar.gz into the current directory
tar -x|--extract -f|--file=foo.tar              # Un-combine foo.tar into the current directory
```

## Disk Usage

```bash
df                     # List disks, size, used, and available space
df -h|--human-readable # List disks, size, used, and available space in a human-readable format

du                     # List current directory, subdirectories, and file sizes
du /foo/bar            # List specified directory, subdirectories, and file sizes
du -h|--human-readable # List current directory, subdirectories, and file sizes in a human-readable format
du -d|--max-depth      # List current directory, subdirectories, and file sizes within the max depth
du -d 0                # List current directory size
```

## Memory Usage

```bash
free                   # Show memory usage
free -h|--human        # Show human-readable memory usage
free -h|--human --si   # Show human-readable memory usage in power of 1000 instead of 1024
free -s|--seconds 5    # Show memory usage and update continuously every five seconds
```

## Packages

```bash
apt update                   # Refresh the repository index
apt search wget              # Search for a package
apt show wget                # List information about the wget package
apt list --all-versions wget # List all versions of the package
apt install wget             # Install the latest version of the wget package
apt install wget=1.2.3       # Install a specific version of the wget package
apt remove wget              # Remove the wget package
apt upgrade                  # Upgrade all upgradable packages
```

## Shutdown and Reboot

```bash
shutdown                     # Shutdown in 1 minute
shutdown now "Cya later"     # Immediately shut down


shutdown +5 "Cya later"      # Shutdown in 5 minutes

shutdown --reboot            # Reboot in 1 minute
shutdown -r now "Cya later"  # Immediately reboot
shutdown -r +5 "Cya later"   # Reboot in 5 minutes

shutdown -c                  # Cancel a shutdown or reboot

reboot                       # Reboot now
reboot -f                    # Force a reboot
```

## Identifying Processes

```bash
top                    # List all processes interactively
htop                   # List all processes interactively
ps all                 # List all processes
pidof foo              # Return the PID of all foo processes

CTRL+Z                 # Suspend a process running in the foreground
bg                     # Resume a suspended process and run in the background
fg                     # Bring the last background process to the foreground
fg 1                   # Bring the background process with the PID to the foreground

sleep 30 &             # Sleep for 30 seconds and move the process into the background
jobs                   # List all background jobs
jobs -p                # List all background jobs with their PID

lsof                   # List all open files and the process using them
lsof -itcp:4000        # Return the process listening on port 4000
```

## Process Priority

Process priorities go from -20 (highest) to 19 (lowest).

```bash
nice -n -20 foo        # Change the process priority by name
renice 20 PID          # Change the process priority by PID
ps -o ni PID           # Return the process priority of PID
```

## Killing Processes

```bash
CTRL+C                 # Kill a process running in the foreground
kill PID               # Shut down the process by PID gracefully. Sends TERM signal.
kill -9 PID            # Force shutdown of the process by PID. Sends SIGKILL signal.
pkill foo              # Shut down the process by name gracefully. Sends TERM signal.
pkill -9 foo           # Force shut down the process by name. Sends SIGKILL signal.
killall foo            # Kill all processes with the specified name gracefully.
```

## Date & Time

```bash
date                   # Print the date and time
date --iso-8601        # Print the ISO8601 date
date --iso-8601=ns     # Print the ISO8601 date and time

time tree              # Time how long the tree command takes to execute
```

## Scheduled Tasks

```pre
   *      *         *         *           *
Minute, Hour, Day of month, Month, Day of the week
```

```bash
crontab -l                 # List the cron tab
crontab -e                 # Edit the cron tab in Vim
crontab /path/crontab      # Load the cron tab from a file
crontab -l > /path/crontab # Save the cron tab to a file

* * * * * foo              # Run foo every minute
*/15 * * * * foo           # Run foo every 15 minutes
0 * * * * foo              # Run foo every hour
15 6 * * * foo             # Run foo daily at 6:15 AM
44 4 * * 5 foo             # Run foo every Friday at 4:44 AM
0 0 1 * * foo              # Run foo at midnight on the first of the month
0 0 1 1 * foo              # Run foo at midnight on the first of the year

at -l                      # List scheduled tasks
at -c 1                    # Show the task with ID 1
at -r 1                    # Remove the task with ID 1
at now + 2 minutes         # Create a task in Vim to execute in 2 minutes
at 12:34 PM next month     # Create a task in Vim to execute at 12:34 PM next month
at tomorrow                # Create a task in Vim to execute tomorrow
```

## HTTP Requests

```bash
curl https://example.com                               # Retrieve response body
curl -i|--include https://example.com                  # Include status code and HTTP headers
curl -L|--location https://example.com                 # Follow redirects
curl -o|--remote-name foo.txt https://example.com      # Save response to a text file
curl -H|--header "User-Agent: Foo" https://example.com # Add a custom HTTP header
curl -X|--request POST -H "Content-Type: application/json" -d|--data '{"foo":"bar"}' https://example.com # POST JSON
curl -X POST -H --data-urlencode foo="bar" http://example.com                           # POST URL Form Encoded

wget https://example.com/file.txt .                            # Download a file to the current directory
wget -O|--output-document foo.txt https://example.com/file.txt # Save response to a file with the specified name
```

## Network Troubleshooting

```bash
ping example.com            # Send multiple ping requests using the ICMP protocol
ping -c 10 -i 5 example.com # Make 10 attempts, 5 seconds apart

ip addr                     # List IP addresses on the system
ip route show               # Show IP addresses to router

netstat -i|--interfaces     # List all network interfaces and in/out usage
netstat -l|--listening      # List all open ports

traceroute example.com      # List all servers the network traffic goes through

mtr -w|--report-wide example.com                                    # Continually list all servers the network traffic goes through
mtr -r|--report -w|--report-wide -c|--report-cycles 100 example.com # Output a report that lists network traffic 100 times

nmap 0.0.0.0                # Scan for the 1000 most common open ports on localhost
nmap 0.0.0.0 -p1-65535      # Scan for open ports on localhost between 1 and 65535
nmap 192.168.4.3            # Scan for the 1000 most common open ports on a remote IP address
nmap -sP 192.168.1.1/24     # Discover all machines on the network by ping'ing them
```

## DNS

```bash
host example.com            # Show the IPv4 and IPv6 addresses

dig example.com             # Show complete DNS information

cat /etc/resolv.conf        # resolv.conf lists nameservers
```

## Hardware

```bash
lsusb                  # List USB devices
lspci                  # List PCI hardware
lshw                   # List all hardware
```

## Terminal Multiplexers

Start multiple terminal sessions. Active sessions persist reboots. `tmux` is more modern than `screen`.

```bash
tmux             # Start a new session (CTRL-b + d to detach)
tmux ls          # List all sessions
tmux attach -t 0 # Reattach to a session

screen           # Start a new session (CTRL-a + d to detach)
screen -ls       # List all sessions
screen -R 31166  # Reattach to a session

exit             # Exit a session
```

## Secure Shell Protocol (SSH)

```bash
ssh hostname                 # Connect to hostname using your current user name over the default SSH port 22
ssh -i foo.pem hostname      # Connect to hostname using the identity file
ssh user@hostname            # Connect to hostname using the user over the default SSH port 22
ssh user@hostname -p 8765    # Connect to hostname using the user over a custom port
ssh ssh://user@hostname:8765 # Connect to hostname using the user over a custom port
```

Set default user and port in `~/.ssh/config`, so you can just enter the name next time:

```bash
$ cat ~/.ssh/config
Host name
  User foo
  Hostname 127.0.0.1
  Port 8765
$ ssh name
```

## Secure Copy

```bash
scp foo.txt ubuntu@hostname:/home/ubuntu # Copy foo.txt into the specified remote directory
```

## Bash Profile

- bash - `.bashrc`
- zsh - `.zshrc`

```bash
# Always run ls after cd
function cd {
  builtin cd "$@" && ls
}

# Prompt user before overwriting any files
alias cp='cp --interactive'
alias mv='mv --interactive'
alias rm='rm --interactive'

# Always show disk usage in a human readable format
alias df='df -h'
alias du='du -h'
```

## Bash Script

### Variables

```bash
#!/bin/bash

foo=123                # Initialize variable foo with 123
declare -i foo=123     # Initialize an integer foo with 123
declare -r foo=123     # Initialize readonly variable foo with 123
echo $foo              # Print variable foo
echo ${foo}_'bar'      # Print

 variable foo followed by _bar
echo ${foo:-'default'} # Print variable foo if it exists otherwise print default

export foo             # Make foo available to child processes
unset foo              # Make foo unavailable to child processes
```

### Environment Variables

```bash
#!/bin/bash

env            # List all environment variables
echo $PATH     # Print PATH environment variable
export FOO=Bar # Set an environment variable
```

### Functions

```bash
#!/bin/bash

greet() {
  local world="World"
  echo "$1 $world"
  return "$1 $world"
}
greet "Hello"
greeting=$(greet "Hello")
```

### Exit Codes

```bash
#!/bin/bash

exit 0   # Exit the script successfully
exit 1   # Exit the script unsuccessfully
echo $?  # Print the last exit code
```

### Conditional Statements

#### Boolean Operators

- `$foo` - Is true
- `!$foo` - Is false

#### Numeric Operators

- `-eq` - Equals
- `-ne` - Not equals
- `-gt` - Greater than
- `-ge` - Greater than or equal to
- `-lt` - Less than
- `-le` - Less than or equal to
- `-e foo.txt` - Check if the file exists
- `-z foo` - Check if the variable exists

#### String Operators

- `=` - Equals
- `==` - Equals
- `-z` - Is null
- `-n` - Is not null
- `<` - Is less than in ASCII alphabetical order
- `>` - Is greater than in ASCII alphabetical order

#### If Statements

```bash
#!/bin/bash

if [[ $foo = 'bar' ]]; then
  echo 'one'
elif [[ $foo = 'bar' ]] || [[ $foo = 'baz' ]]; then
  echo 'two'
elif [[ $foo = 'ban' ]] && [[ $USER = 'bat' ]]; then
  echo 'three'
else
  echo 'four'
fi
```

#### Inline If Statements

```bash
#!/bin/bash

[[ $USER = 'rehan' ]] && echo 'yes' || echo 'no'
```

#### While Loops

```bash
#!/bin/bash

declare -i counter
counter=10
while [[ $counter -gt 2 ]]; do
  echo The counter is $counter
  counter=counter-1
done
```

#### For Loops

```bash
#!/bin/bash

for i in {0..10..2}
  do
    echo "Index: $i"
  done

for filename in file1 file2 file3
  do
    echo "Content: " >> $filename
  done

for filename in *;
  do
    echo "Content: " >> $filename
  done
```

#### Case Statements

```bash
#!/bin/bash

echo "What's the weather like tomorrow?"
read weather

case $weather in
  sunny | warm ) echo "Nice weather: " $weather
  ;;
  cloudy | cool ) echo "Not bad weather: " $weather
  ;;
  rainy | cold ) echo "Terrible weather: " $weather
  ;;
  * ) echo "Don't understand"
  ;;
esac
```

### Script to Check Disk Usage

```bash
#!/bin/bash

disk_usage=$(df -h | grep '/dev/sda1')
echo "Disk Usage Information:"
echo "$disk_usage"
```

### Script to Monitor CPU Usage

```bash
#!/bin/bash

cpu_usage=$(top -bn1 | grep "Cpu(s)" | sed "s/.*, *\([0-9.]*\)%* id.*/\1/" | awk '{print 100 - $1"%"}')
echo "CPU Usage: $cpu_usage"
```

### Script to Display System Information

```bash
#!/bin/bash

echo "System Information:"
echo "Hostname: $(hostname)"
echo "Operating System: $(uname -s)"
echo "Kernel Version: $(uname -r)"
echo "CPU Architecture: $(uname -m)"
echo "Total Memory: $(free -h | awk '/Mem/{print $2}')"
echo "Available Memory: $(free -h | awk '/Mem/{print $7}')"
echo "Uptime: $(uptime -p)"
```

### Script to Backup Files

```bash
#!/bin/bash

backup_dir="/path/to/backup"
source_dir="/path/to/source"

timestamp=$(date +%Y%m%d%H%M%S)
backup_file="backup_$timestamp.tar.gz"

echo "Creating backup..."
tar -czf "$backup_dir/$backup_file" "$source_dir"
echo "Backup created: $backup_file"
```

### Script to Check Network Connectivity

```bash
#!/bin/bash

ping_result=$(ping -c 4 google.com)

if [[ $? -eq 0 ]]; then
  echo "Network is reachable."
else
  echo "Network is unreachable."
fi
```

### Script to Check Available Memory

```bash
#!/bin/bash

available_memory=$(free -h | awk '/Mem/{print $7}')
echo "Available Memory: $available_memory"
```

### Script to Monitor Disk Usage of a Specific Directory

```bash
#!/bin/bash

directory="/path/to/directory"
disk_usage=$(du -sh "$directory" 2>/dev/null | cut -f1)

if [[ -z $disk_usage ]]; then
  echo "Directory not found or permission denied."
else
  echo "Disk Usage of $directory: $disk_usage"
fi
```

### Script to List Running Processes

```bash
#!/bin/bash

echo "Running Processes:"
ps aux
```

### Script to Display Current Date and Time

```bash
#!/bin/bash

current_datetime=$(date +"%Y-%m-%d %H:%M:%S")
echo "Current Date and Time: $current_datetime"
```

### Script to Generate Random Password

```bash
#!/bin/bash

password=$(openssl rand -base64 12)
echo "Generated Password: $password"
```

### Script to Check System Load Average

```bash
#!/bin/bash

load_average=$(cat /proc/loadavg | awk '{print $1, $2, $3}')
echo "System Load Average: $load_average"
```

### Script to Monitor Network Traffic

```bash
#!/bin/bash

echo "Network Traffic:"
netstat -i
```

### Script to Search for a File

```bash
#!/bin/bash

file_to_search="filename"
echo "Searching for $file_to_search..."
find / -name "$file_to_search" 2>/dev/null
```

### Script to Display System Users

```bash
#!/bin/bash

echo "System Users:"
cut -d: -f1 /etc/passwd
```

### Script to Check System Uptime

```bash
#!/bin/bash

uptime=$(uptime)
echo "System Uptime: $uptime"
```

## Input Output Redirectors

```bash
cmd1|cmd2  # Pipe; takes standard output of cmd1 as standard input to cmd2
< file     # Takes standard input from file
> file     # Directs standard output to file
>> file    # Directs standard output to file; append to file if it already exists
>|file     # Forces standard output to file even if noclobber is set
n>|file    # Forces output to file from file descriptor n even if noclobber is set
<> file    # Uses file as both standard input and standard output
n<>file    # Uses file as both input and output for file descriptor n
n>file     # Directs file descriptor n to file
n<file     # Takes file descriptor n from file
n>>file    # Directs file description n to file; append to file if it already exists
n>&        # Duplicates standard output to file descriptor n
n<&        # Duplicates standard input from file descriptor n
n>&m       # File descriptor n is made to be a copy of the output file descriptor
n<&m       # File descriptor n is made to be a copy of the input file descriptor
&>file     # Directs standard output and standard error to file
<&-        # Closes the standard input
>&-        # Closes the standard output
n>&-       # Closes the output from file descriptor n
n<&-       # Closes the input from file descriptor n

|tee <file># Output command to both terminal and a file (-a to append to file)
```

## Command Line Processing Cycle

```bash
command  # Removes alias and function lookup. Only built-ins and commands found in the search path are executed
builtin  # Looks up only built-in commands, ignoring functions and commands found in PATH
enable   # Enables and disables shell built-ins

eval     # Takes arguments and runs them through the command-line processing steps all over again
trap     # Sets up signal handling for the shell, allowing you to execute commands when signals are received
```

## Debugging Shell Scripts

```bash
# Check for syntax errors without executing commands
bash -n scriptname
set -o noexec  # Alternative (set option in script)

# Echo commands before running them
bash -v scriptname
set -o verbose  # Alternative (set option in script)

# Echo commands after command-line processing
bash -x scriptname
set -o xtrace  # Alternative (set option in script)

# Print out the values of variables at script exit
trap 'echo $varname' EXIT

function errtrap {
  es=$?
  echo "ERROR line $1: Command exited with status $es."
}

# Run whenever a command exits with non-zero status
trap 'errtrap $LINENO' ERR

function dbgtrap {
  echo "badvar is $badvar"
}

# Execute before every statement in a function or script
trap dbgtrap DEBUG

# Turn off the DEBUG trap after the problematic section
trap - DEBUG

function returntrap {
  echo "A return occurred"
}

# Execute each time a shell function or a script finishes executing
trap returntrap RETURN
```

## Colors and Styles

```bash
# Note: \e or \x1B also work instead of \033

# Reset
Color_Off='\033[0m' # Text Reset

# Regular Colors
Black='\033[0;30m'  # Black
Red='\033[0;31m'    # Red
Green='\033[0;32m'  # Green
Yellow='\033[0;33m' # Yellow
Blue='\033[0;34m'   # Blue
Purple='\033[0;35m' # Purple
Cyan='\033[0;36m'   # Cyan
White='\033[0;97m'  # White

# Additional colors
LGrey='\033[0;37m'  # Light Gray
DGrey='\033[0;90m'  # Dark Gray
LRed='\033[0;91m'   # Light Red
LGreen='\033[0;92m' # Light Green
LYellow='\033[0;93m'# Light Yellow
LBlue='\033[0;94m'  # Light Blue
LPurple='\033[0;95m'# Light Purple
LCyan='\033[0;96m'  # Light Cyan

# Bold
BBlack='\033[1;30m' # Black
BRed='\033[1;31m'   # Red
BGreen='\033[1;32m' # Green
BYellow='\033[1;33m'# Yellow
BBlue='\033[1;34m'  # Blue
BPurple='\033[1;35m'# Purple
BCyan='\033[1;36m'  # Cyan
BWhite='\033[1;37m' # White

# Underline
UBlack='\033[4;30m' # Black
URed='\033[4;31m'   # Red
UGreen='\033[4;32m' # Green
UYellow='\033[4;33m'# Yellow
UBlue='\033[4;34m'  # Blue
UPurple='\033[4;35m'# Purple
UCyan='\033[4;36m'  # Cyan
UWhite='\033[4;37m' # White

# Background
On_Black='\033[40m' # Black
On_Red='\033[41m'   # Red
On_Green='\033[42m' # Green
On_Yellow='\033[43m'# Yellow
On_Blue='\033[44m'  # Blue
On_Purple='\033[45m'# Purple
On_Cyan='\033[46m'  # Cyan
On_White='\033[47m' # White

# Example of usage
echo -e "${Green}This is GREEN text${Color_Off} and normal text"
echo -e "${Red}${On_White}This is Red text on White background${Color_Off}"
# Option -e is mandatory, it enables interpretation of backslash escapes
printf "${Red} This is red \n"
```

## Tips and Tricks

```bash
# Set an alias
cd; nano .bash_profile
> alias gentlenode='ssh admin@gentlenode.com -p 3404'  # Add your alias in .bash_profile

# To quickly go to a specific directory
cd; nano .bashrc
> shopt -s cdable_vars
> export websites="/Users/mac/Documents/websites"

source .bashrc
cd $websites

# Shortcut for going back to the previous directory
cd -

# Quickly create a new directory and navigate into it
mkcd() { mkdir -p "$@" && cd "$1"; }

# Easily extract compressed files
extract() {
    if [ -f "$1" ] ; then
        case $1 in
            *.tar.bz2)   tar xvjf "$1"     ;;
            *.tar.gz)    tar xvzf "$1"     ;;
            *.tar.xz)    tar xvJf "$1"     ;;
            *.bz2)       bunzip2 "$1"      ;;
            *.rar)       unrar x "$1"      ;;
            *.gz)        gunzip "$1"       ;;
            *.tar)       tar xvf "$1"      ;;
            *.tbz2)      tar xvjf "$1"     ;;
            *.tgz)       tar xvzf "$1"     ;;
            *.zip)       unzip "$1"        ;;
            *.Z)         uncompress "$1"   ;;
            *.7z)        7z x "$1"         ;;
            *)           echo "'$1' cannot be extracted" ;;
        esac
    else
        echo "'$1' is not a valid file"
    fi
}

# Generate a random string
random_string() {
    head /dev/urandom | tr -dc A-Za-z0-9 | head -c ${1:-32}
}

# Quick search for a command in the history
histgrep() {
    history | grep "$@"
}

# Display a progress bar while running a command
progressbar() {
    local duration="${1}"
    local cols=$(tput cols)
    local fillchar="█"
    local progresschar="▌"
    local blankchar="░"
    local progress=""
    local percentage=""
    local elapsed="0"

    while [ "${elapsed}" -lt "${duration}" ]; do
        percentage=$(( elapsed * 100 / duration ))
        progress=$(( cols * percentage / 100 ))
        printf "\r${fillchar}%-${progress}s${blankchar}%-$(( cols - progress ))s ${percentage}%%" | tr ' ' "${progresschar}"
        sleep 1
        (( elapsed++ ))
    done

    printf "\n"
}

# Show disk usage for current directory sorted by size
duh() {
    du -h --max-depth=1 | sort -hr
}

# Find a file with a pattern in the current directory and its subdirectories
findf() {
    find . -type f -iname "*$1*"
}

# Print the last few lines of a file
tailn() {
    tail -n "${1:-10}"
}

# Open the current directory in a file explorer
opendir() {
    if command -v xdg-open >/dev/null 2>&1; then
        xdg-open .
    elif command -v open >/dev/null 2>&1; then
        open .
    elif command -v explorer >/dev/null 2>&1; then
        explorer .
    else
        echo "Could not detect a supported file explorer."
    fi
}

# Count the number of lines in a file
linecount() {
    wc -l < "$1"
}

# Convert Markdown files to HTML using pandoc
md2html() {
    if [ $# -eq 0 ]; then
        echo "Usage: md2html <input_file.md> [output_file.html]"
        return 1
    fi
    input_file="$1"
    output_file="${2:-${input_file%.md}.html}"
    pandoc -s -o "$output_file" "$input_file"
    echo "HTML file generated: $output_file"
}

# Quickly access frequently used directories with bookmarks
bookmark() {
    case $1 in
        add)
            if [ $# -eq 2 ]; then
                echo "alias $2='cd $(pwd)'" >> ~/.bashrc
                source ~/.bashrc
                echo "Bookmark added for $(pwd)"
            else
                echo "Usage: bookmark add <alias>"
            fi
            ;;
        remove)
            if [ $# -eq 2 ]; then
                sed -i "/alias $2=/d" ~/.bashrc
                unalias "$2"
                source ~/.bashrc
                echo "Bookmark removed: $2"
            else
                echo "Usage: bookmark remove <alias>"
            fi
            ;;
        list)
            grep "alias " ~/.bashrc | grep -oP "(?<=alias ).*(?=')"
            ;;
        *)
            echo "Usage: bookmark [add|remove|list]"
            ;;
    esac
}

# Quickly convert images to a different format
convert_image() {
    if [ $# -lt 2 ]; then
        echo "Usage: convert_image <input_file> <output_format>"
        return 1
    fi
    input_file="$1"
    output_format="$2"
    output_file="${input_file%.*}.$output_format"
    convert "$input_file" "$output_file"
    echo "Image converted to $output_format: $output_file"
}
```

## Shortcut Keys

```bash
#!/bin/bash

# Movement Shortcuts
CTRL+A  # Move to the beginning of the line
CTRL+B  # Move backward one character
CTRL+E  # Move to the end of the line
CTRL+F  # Move forward one character
ALT+B   # Move backward one word
ALT+F   # Move forward one word

# Deletion Shortcuts
CTRL+D  # Delete one character backward or log out of the current session
CTRL+H  # Delete one character under the cursor (same as DELETE)
CTRL+K  # Delete forward to the end of the line
CTRL+W  # Delete the word behind the cursor
ALT+D   # Delete the next word
ALT+H   # Delete one character backward

# Line Editing Shortcuts
CTRL+C  # Halt the current command
CTRL+G  # Abort the current editing command and ring the terminal bell
CTRL+L  # Clear the screen and redisplay the line
CTRL+M  # Same as RETURN
CTRL+J  # Same as RETURN
CTRL+N  # Move to the next line in command history
CTRL+P  # Move to the previous line in command history
CTRL+Q  # Resume suspended shell output
CTRL+R  # Search backward
CTRL+S  # Search forward or suspend shell output
CTRL+T  # Transpose two characters
CTRL+U  # Kill backward from the point to the beginning of the line
CTRL+V  # Make the next character typed verbatim
CTRL+Y  # Retrieve (yank) the last item killed
CTRL+Z  # Stop the current command, resume with fg in the foreground or bg in the background

# Word Editing Shortcuts
ALT+T   # Transpose two words
ALT+U   # Capitalize every character from the current cursor position to the end of the word
ALT+L   # Uncapitalize every character from the current cursor position to the end of the word
ALT+C   # Capitalize the letter under the cursor
ALT+R   # Revert any changes to a command pulled from history
ALT+?   # List possible completions for what is typed
ALT+^   # Expand line to the most recent match from history

# Other Shortcuts
CTRL+X then (       # Start recording a keyboard macro
CTRL+X then )       # Finish recording keyboard macro
CTRL+X then E       # Invoke text editor specified by $EDITOR on current command line then execute results as shell commands
CTRL+A then D       # Logout from screen but don't kill it, if any command exists, it will continue

# Character Deletion Shortcuts
BACKSPACE  # Delete one character backward
DELETE     # Delete one character under the cursor
```

## Best Practices

Follow best practices to write clean and maintainable Bash scripts:

- Use meaningful variable names.
- Add comments to explain complex sections.
- Check for errors and handle them gracefully.

## Contributing

We welcome contributions from the community! If you have improvements or additional content to add, please follow our [contribution guidelines](CONTRIBUTING.md).

## License

This Bash Scripting Cheat Sheet is licensed under the [MIT License](LICENSE.md). Feel free to use, share, and modify the content as per the terms of the license.

<h3 align='center'>🎉 😃 Happy Scripting 🚀 🎉 </h3>
