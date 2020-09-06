# Linux Cheatsheet
600+ distros\
Package management -> apt-get: Debian, apt: Ubuntu, yum: RHEL, dnf: Fedora\
<img src="arch.png" width="400">\
Shell - interface\
Kernel - A core component of OS that manages communication between HW & SW.\
OS = Kernel Space + User Space\
User Space = GUI, file system, text editor, compiler, sys admin cmds.\
Microkernel Architecture: Bare minimum code to run in kernel space and the rest in user space.\
Some key characteristics of kernel include Basic IPC, Virtual Memory Mgmt., Scheduling.

## Useful Linux commands
NOTE: No command in caps.

`pwd` is print working directory.\
`grep` is general regular expression pattern.
```
grep -inc RAM user.txt
```
i - case insensitive, n - line #, c - # of times matched.
```
( ) | grep "Star Wars"
```

`awk` used for text data extraction, like from a .csv file.
```
awk -F: '{print $1, "-->" $NF}' /etc/passwd
```

`ssh` is replacement for `telnet`. `telnet` is not secure.
```
ssh <ip-addr>
```
On server, to check if sshd is running
```
systemctl status sshd
```
From client,
```
ssh -p 2201 <server-ip-addr>
```
If not root, user "ram" can with password (by default) access remote server\
```
ssh -p 2201 ram@<server-ip-addr>
```

Network swiss-army-knife `netcat`\
```
netcat -l 8080
netcat <server-ip-addr> 2201
```
o/p will inform if port 2201 is open.

To Compress ----> `tar -cvf <tar-file> <source-folder>`\
To Decompress --> `tar -xvf <tar-file>`

How to Set Static IP Address and Configure Network in Linux [[Click Here](https://www.tecmint.com/set-add-static-ip-address-in-linux/)]

### Print out contents of multiple files with filenames:
#### Approach 1:
```
$ for i in *
> do
> echo $i
> cat $i
> done
```
Output:\
board_fp_subtype\
XENONboard_subtype\
XENONboard_type

#### Approach 2:
```
$ find ./ -type f |  xargs tail -n +1
```
Output:\
==> ./sfp3_config <==\
BADACCE5

### Save debugs messages from *mem_table.txt* onto a log file:
```
echo "Contents of mem_table.txt: " >> debug_script.log
var1="$(cat /etc/mem_table.txt)"
echo "$var1" >> debug_script.log
```

### Script not executing the piece of code you added in it?
#### Let `set_config` be the function of interest and `config` be the flag inside that function.
In your linux shell, run:
```
source /etc/init_common.sh
set_config
echo $config
```
