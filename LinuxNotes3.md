# Linux/Bash-Notes [3]  - #!/bin/bash echo "skidrow;Linux-Notes!"

// Linux Notes 03  //  - Skidrow  

- Linux must at least 1 file system (ie. root: /)
-Distros: 
Ubuntu, Debian, Fedora, Mint, Kali, etc
CentOS is lite version of RedHat Enterprise Linux
-sh - Bourne shell (Original Unix)
- bash - Bourne-again shell
Getting Help: 
- man pages - details to CLI commands
- apropos - search the name of section of all man pages
- whatis - display a brief description of the given command
info - display information page of a command 
Linux Users : 
root = Superuser Do = Admin tasks ID (uid) is always 0 
Regular user = Non-root - ID 1000 or more 
Substitute/Switch User
- su
- Switch user creds : su - someuser
- su -root / sudo su - Switches to creds to root user
sudo : Enables server admin to delegate commands to users without full privelages User of this command must be in /etc/sudoers
Sticky Bit - Special permission bit that protects files in a directory
