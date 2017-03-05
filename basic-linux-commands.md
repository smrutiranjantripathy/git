# Basic Linux Commands
Regularly used linux commands

  * **Alias:** To get a list aliases,currently configured in your system.
  
  `alias`
  
###Standard Input Output:
----------------------
```
STDIN <0
STDOUT 1> ( to o/p) 1>> (to append output)
STDERR 2> 
2> & 1 ( Redirects STDERR at  the same destination as STDOUT)
```
**Device files:** Are used to access specific devices.
Your hard disk for instance can be referred to as `/dev/sda`, the console of your server is known as `/dev/console` or `/dev/tty1`, and if you want to discard a commands output, you can redirect to `/dev/null`.

`history -c`  to clean history.

`history -w`  to delete history file.

`/etc/profile`: This is the generic file that is processed by all users upon login.

`/etc/bashrc`: This file is processed when subshells are started.

`~/.bash_profile`: In this file, user-specific login shell variables can be defined.

`~/.bashrc`: In this user-specific file, subshell variables can be defined.

  
 


