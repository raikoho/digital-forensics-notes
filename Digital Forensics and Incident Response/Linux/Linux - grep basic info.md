## OS release information

cat /etc/os-release`

## User accounts

`cat /etc/passwd| column -t -s :`

## Group Information

`cat /etc/group`

## Sudoers List

`sudo cat /etc/sudoers`

## Login information

`sudo last -f /var/log/wtmp`

## Authentication logs

`cat /var/log/auth.log |tail`

## Hostname
```
user@machine$ cat /etc/hostname 
tryhackme
```

## Timezone
```
user@machine$ cat /etc/timezone 
Etc/UTC
```

## Network Configuration

```
cat /etc/network/interfaces
ip address show
```

## Active network connections

```
netstat -natp
```

## Running processes

```
user@machine$ ps aux
```

## DNS information

```
cat /etc/hosts
cat /etc/resolv.conf
```

## Cron jobs

Cron jobs are commands that run periodically after a set amount of time.
```
cat /etc/crontab
```

## Service startup

Like Windows, services can be set up in Linux that will start and run in the background after every system boot.
```
ls /etc/init.d/
```

## .Bashrc

When a bash shell is spawned, it runs the commands stored in the `.bashrc` file.
```
cat ~/.bashrc
```

## Sudo execution history

All the commands that are run on a Linux host using `sudo` are stored in the auth log.
```
cat /var/log/auth.log* |grep -i COMMAND|tail
```
"COMMAND" = adduser, install etc...

**Example:**
A script file was saved using the "vi" text editor. What is the name of this file?

``cat home/NAME_OF_USER/.viminfo | grep saveas``

A script file was opened using the "vi" text editor. What is the name of this file?

``cat /var/log/auth.log* |grep -i vi``
## Bash history

Any commands other than the ones run using `sudo` are stored in the bash history
```
cat ~/.bash_history
```

## Files accessed using vim

file contains command line history, search string history, etc. for the opened files
```
cat ~/.viminfo
```

## Syslog

The Syslog contains messages that are recorded by the host about system activity.
```
cat /var/log/syslog* | head
```

## Auth logs

The auth logs contain information about users and authentication-related logs.
```
cat /var/log/auth.log* |head
```

## Third-party logs

Similar to the syslog and authentication logs, the `/var/log/` directory contains logs for third-party applications such as webserver, database, or file share server logs.
```
ls /var/log
ls /var/log/apache2/
```

## Example

The machine earlier had a different hostname. What was the previous hostname of the machine?

```
cat /var/log/syslog* | grep hostname
```

When the file was last time modifiend?
```
> ls -l /bin/os-update.sh

-rw-r--r-- 1 root root 325 Dec 28  2022 /bin/os-update.sh
```

