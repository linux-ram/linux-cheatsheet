# Linux Cheatsheet
## Useful Linux commands

`pwd` is print working directory.\
`grep` is general regular expression pattern.

To Compress ----> `tar -**c**vf [tar-file] [source-folder]`\
To Decompress --> `tar -**x**vf [tar-file]`


[How to Set Static IP Address and Configure Network in Linux:](https://www.tecmint.com/set-add-static-ip-address-in-linux/)

### Print out contents of multiple files with filenames:
`$ for i in *
> do 
> echo $i
> cat $i
> done
Output:
board_fp_subtype
XENONboard_subtype
XENONboard_type`

`$ find ./ -type f |  xargs tail -n +1
Output:
==> ./sfp3_config <==
BADACCE5`

### Save debugs messages onto a file:
`echo "Contents of mem_table.txt: " >> debug_script.log
var1="$(cat /etc/mem_table.txt)"
echo "$var1" >> debug_script.log`

### Script not executing the piece of code you added in it?
In your linux shell, run:
`source /etc/init_common.sh
set_config
echo $config`
