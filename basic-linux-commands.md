# Basic Linux Commands
Regularly used linux commands

  * **Alias:** To get a list aliases,currently configured in your system.
  
  `alias`
  
  
`type < command name> `: To check whether it is external or internal command.  
  
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

`LANG` varibale is used to set the language for linux.

*To fileter the output of man with respect system administration:*

* 1: Executable programs or shell commands
* 5: File formats and conventions
* 8: System administration commands

**example:**
`man -k partition | grep 8`

To update man pages:
`sudo mandb`

`info` command also prvides information.

Some important points of documenattion are found at /usr/share/doc. ( That may contain critical administrative tasks).

To edit the welcome message /etc/issue.
`/etc/motd` - Displays the messgae after a user is logged in.

For Ubuntu Based Systems these files will be found at:
`/etc/update-motd.d/`
Details: http://www.howtogeek.com/104708/how-to-customize-ubuntus-message-of-the-day/

File descriptor A pointer that is used by a Linux process to refer to files that are in use by the process.

Shell The environment from which commands can be executed. Bash is the default shell on Linux, but other shells exist as well.

**Internal command:** A command that is a part of the shell and does not exist as a file on disk.
**External command:** A command that exists as a file on disk.

**Path:** The complete reference to the location of a file.

**Pipe:** A structure that can be used to forward the output of one command to be
used as input for another command

**Redirect:** Method where something is sent somewhere else. Used mainly in DNS.

**Device file:** A file that is created in the /dev directory and that is used to represent
and interact with a device.

**Environment:** The collection of settings that users or processes are using to do their work.

**Subshell:** A shell that is started from another shell. Typically, by running a shell
script a subshell is started.

**Login shell:** The shell that is opened directly after a user has logged in.

Note:

*File System Info*

**The default file system of Red Hat "XFS".Key Differnce between XFS and EXT4
Size of a file system can't be reduced in XFS.**


When configuring LVM you will get 3 volumes 
 * /boot,
 * / ,
 * swp but not /home.
 
 If we want a variable to be processed by all users then we need to define the file in ~/etc/profile.
 
 `/` The root directory. This is where the file system tree starts.

`/bin`: In here, you find executable programs that are needed to repair a system in
a minimal troubleshooting mode. This directory is essential during boot.

`/boot`: Contains all files and directories that are needed to boot the Linux kernel.

`/dev`: Device files that are used for accessing physical devices. This directory is
essential during boot.

`/etc`: Contains configuration files that are used by programs and services that
are used on your server. This directory is essential during boot.

`/home`: Used for local user home directories.

`/lib`, `/lib64` Shared libraries that are used by programs in /boot, /bin and /sbin.

`/media`, `/mnt` Directories that are used for mounting devices in the file system tree.

`/opt` This directory is used for optional packages that may be installed on your
server.

`/proc`: This directory is used by the proc file system. This is a file system structure that gives access to kernel information.

`/root`: The home directory of the root user.

`/run`: Contains process and user specific information that has been created since
the last boot.

`/sbin`: Like `/bin`, but for system administration commands that are not necessarily needed by regular users.

###To get the list of mounts 
mount command which reads from /proc/mount.

`df -Th` - To see mounts and the file system.

Wildcard Use

`*` Refers to an unlimited number of all characters. `ls *` , for instance, shows all files
in the current directory (except those that have a name starting with a dot).

`?` Used to refer to one specific character that can be any character. ls c?t would
match cat as well as cut.

`[auo]` Refers to one character that may be selected from the range that is specified
between square brackets. ls c[auo]t would match cat, cut, and cot.

While using the cp command, permissions and other properties of the files are to
be considered. Without extra options, you risk permissions not being copied. If you
want to make sure that you keep the current permissions, use the `-a `option, which
has cp work in archive mode.

 * cp /somedir/.* /tmp This copies all files that have a name starting with a
dot (the hidden files, that is) to /tmp. It gives an error message for directories
whose name starts with a dot in /somedir, because the -R option was not used.

 * cp -a /somedir/ . This copies the entire directory /somedir, including its
contents, to the current directory. So, as a result, a subdirectory somedir will
be created in the current directory.

* cp -a /somedir/. . This copies all files, regular and hidden, to the current directory.



























  
 


