# Linux/Bash-Notes [1]  - #!/bin/bash echo "skidrow;Linux-Notes!"

// Linux Course Notes //  - Skidrow  


- Unix , Linux , Minix , C Lang , 

// Introducation  //
- GNU -->  Linux -->  System Kernel  
- GNU - OS  , UNIX   - OS  Linux - Kernel  , 
- Components  [ Bootloader , Kernel , Init System , Daemons , Graphical Server , Desktop Env , Applications  ]
- Desktop Environments - Gnome , KDE ,XFCE  , LXDE , Open box 
-Linux Distros :   Debian  , RedHat , Centos , Arch , Kali ,Parrot , .. etc 
- Different in Distros  - Package Manger 
- Stdin = Standar Input [$0] , Stdout-Standrdoutput [$1] , StandardError[$2] 
-d directories 
- normal file to open
 - Bash Born Again Shlee 
 - $SHELL = Type of Shell ;
 - $PATH = Path 
 - $USER = CurrentUser
 - $HOSTNAME = hostname
 - $? = exit code
 - up and Down Arrow (Previous Commands History) 
 - Linux is Case_Senstive 
 - Tab Key = Auto_Complete 
 - ~ home dir
 . is Current Dir  
.. is parent directory
 - login shell , non-login shell 
 - /etc/profile
 - /etc/login.defs
 - /etc/default/useradd
 - /etc/adduser.conf
 - /etc/skel/
 - /etc/fstab
 - /etc/sudoers
 - inode = metadata , location 
 - stat  
 - dmidecode ,dmesg , journalctl , smartctl , systemctl , lspci , sensors , htop , top , vmstat , lsblk  , lsmod , cpio , iostat , sar  , vmstat
// 
 - top - system info , ram , cpu , .. etc 
 - cd , pwd , ls , ip a , ifconfig , iwconfig , clear , echo 
 - mkdir , rmdir , rm -rf , cp , mv  , man  , cat , touch 
 - Absolute path /home/kali/  , relative path cd Documents 
 - > export < open >> apend  
 - less , head, tail , sort , uniq , grep , more , file , tee , tree , history , alias , 
 - find , locate  , updatedb  , pushd  , popd 
 - * wildcard ,  . - hidden file  - Link file  , & and  && if first works then .. , {range}  
 - - crontab -e  ,  time (5 )  , action  , crontab - l , 
 - tar cvf backup.tar    ,  tar  xfv backup.tar  , gzip , unzip  ,gunzip
 - find  / -type f -name  " name "   , *test*.txt , *test*.* 
 - journalctl ,  pgrep - l '^dd$' , watch -n 5 kill  -USR1  , jobs ,fg ,bg 
- scp  , grep  , grep -r "failed" * , df , du , su , diff 
- ssh -keygen -t rsa , ssh-copy-id user@server , ssh root@ip 
- vim , i , esc , shift+zz  
 - wc , cut , awk  , sed , nano , tr ,  vi , vim  , split , who, last , uname , date ,uptime , hostname , which , cal , bc   , whatis , shred 
 - wget , ssh , shutdown , reboot  , systemctl , service , free -h  , ps , kill , killall , hostnamectl , nmtui , nmcli , loginctl  
 // Groups , Users , Permissions // 
 - Groups  Manamgnet   - addgroup , delgroup  , /etc/group , groupmod ,getent group ,groupadd,groupdel
 - Users Manamgnet  , adduser ,deluser, /etc/passwd , useradd ,passwd ,gpasswd ,userdel  , chfn  , chage
 - Permissions  , r  (4) - ( read ) , w ( 2 ) - (write ) , x (1 ) -  (execute) 
- rwx , rwx ,rwx ( User,Group,Others) 
 - u+x - give user execute , u-x  - remove user execute 
 - 9 Permissions(/3)  = { u=rwx,g=rwx,o=rwx } , a = all 
 0= - - - ( nothing )
 1= - - x (execute)
 2= - w - (write)
 3= - w x ( write,execute)
 4= r - - ( read )
 5= r - x ( read,execute)
 6= rw -  (read,write)
 7= rwx = ( all) 
 - getfacl = file ACL  , setfacl 
 - chattr  , lsattr 
- chmod , chown ,chgrp 
- whoami , id , groups  ,usermod ,gtent 
- su - , su , suddeors , passwd,shadow , sudo -l , sudo su
- * account disabled , ! - password not set  , x - password is at shadow file 
- Speical Permssions = S(SUID - 4 ) S(SGID - 2 ) T(Stickybit - 1)
- Mode = Type , User, Group , Other 

  // update & upgrade // 

 - apt , seach , purge , install  , sources  , update ,upgrade , clean , fix-missing , dpkg -i


 // 
 
// Linux  File Sturcutre // 


/bin - Binary executables 
/boot   for boot files 
/cdroom - cd drives
/dev - devices connected
/etc - system config
/home  - user dirs. 
/lib - System Libaries 
/media  - usb drives 
/mnt / temp install for devices 
/opt  for external apps 
/proc system process 
/root  user root dir system admin
/run for apps need to run files
/sbin  system binaries  executable 
/snap for install apps and manage them 
/srv - for servers dirs 
/sys  system files 
/temp temproary files 
/usr  shared files for all users
/var changagble files dir such as logs .. 
- vimlinuz = version of kernal 
- boot/grub - boot loader

//
// Linux Process  // 

 - ps   -a , -e  , -l  , -f  , -efl 
 - top , htop 
 - pkill , kill , killall , 
 - systemd - id (1 )  - first process 
 - ? = process run by kernal without terminal 
 - PID = Process ID 
 - PPID =  Parent Process ID 
 - pstree = tree of process 
 - & background , jobs , bg , fg  , ctrl +z = background  , ctrl + c = kill /quit  
 - Job Id  
 - SIGHUP - restart process with same PID 
 - SIGINT - STOP PROCESS AND CLEAR ( CTRL + C ) 
 - SIGTERM - end PID with  Child Process avoid become Zombie 
 - SIGKILL - Kill 
 - systemctl  , status , start , stop , enable  .. etc 
 - lsof 
 
 //
 
  // Linux Software Packages Manamgnet   // 
  
  - RPM  - RedHat Package Mananger  - yum , dnf 
  - DEB  - Debian Package Manager   - Dpkg  , APT 
  - dpkg - l  , -p  , -i  , -S 
  - apt , upgrade , update ,full-upgrade , dist-upgrade , -y ,  autoremove ,  search , list , --fix--missing 
  
  //
  
  - ssh , ssh-keygen , scp , .ssh , public , private  ssh user@ip ss-i  , kownhosts , authorized_keys  , rsync  , curl , wget 
//  

  // Linux Scripting // 
- sh , 
#!/bin/bash - shbang  - default bash script 
#!/bin/env python3 - if location is not known 
python3-pip  - install python libary


// Other Stuff //

 // Path //  -> Two ways of locating a file or a directory 
 1 .  Absolute Path -> Full path ->  Traces a path from root to a file or a directory -> Always begins with the root (/) directory
 2.   Relative Path -> Traces a path from the ‘cwd’ to a file or a directory ->  No initial forward slash (/) 
 3 . $ - for normal user  
 4 . # - for root user
 
// 
 
 // Partitionion // 
 
 - MBR  - 4 , GPT  - 128 
 -fdisk,gdisk,parted ,mkfs , partprobe , lsblk , e2label , fsck , tune2fs , resize2fs , dumpe2fs , du , df 
 - ext4, xfs , btrfs , mount  , e2fsck .. etc  
 - Raid0  - Faster 
 - Raid1  - Mirror copy 1 to 2 
 - Raid5  - Faster And Backup ( need 3 disks ) 
 - Raid6  - extra backp - slower
 - Raid10 - Combo of Mirror and Striping 
 - hda = hardrive , sda = serial drive 

 // 
-  - Troublshoot  - - 
- lspci   = connected drives 
- lsusb   = connected usb devices 
- dmidecode  = dump bios to file 
- blkid = show block id and uids 
- chroot - security jail 
  // 
 
  // Partitionion  LVM //  
   - pvs , vgs , lvs , lvchange , lvcreate , vgcreate , lvresize , pvcreate , vgextend 
   - Device Mapper 
   - Volume Groups , Physical Volumes , Logical Volumes 
  
  //
   
 
 // File Name Expansion & Wildcards //
* ->    Match zero or more char ->ls *.c
? ->    Match any single character -> ls conf.? 
[list]-> Match any single character in list -> ls conf.[co]
[lower-upper] -> Match any character in rangels -> lib-id[3-7].o
str{str1,str2,...} ]-> Expand str with contents of { } ]-> ls c*.{700,300}

Directory Names // 
– Uppercase letters (A-Z)
– Lowercase letters (a-z)
– Numbers (0-9)
– Underscore ( _ )
– Period/dot ( . )
- ^ Begning 
- $ End 
//


// Cron Jobs // 
- /var/spool/cron
- etc/cron.d / 
- etc/crontab 

Format : -min hour day(of month) , month (dayof week ) [user] , command 
- Min (0-59)
- hour (0-23)
- day of month (1-31)
- month (1-12 ) or month names 
- day of week (0-6 ) 
- username
- command to execute 
- /5  = every 5 min 
- crontab -e  = edit 
- crontab -l  = show tabtable
- crontab -r  = delete 
 = Example =  cat /etc/crontab
 */2 * * * * echo "test" > test.txt/home/kali
//

// Networking // 
- Hostname ,Domain , IP/Subnet , Defualt GW , DNS Server 
- FQDN 
- ip add , ip a , ss , arp  , dig , nslookup , curl , host  , whois , ping , traceroute , netstat , tcpdump , wireshark , mtr , route 
- nmcli , nmtui , tshark 
- Path for Connections : /etc/NetworkManager/system-connections
- DNS Resolve = /etc/resolv.conf
- Servivces = /etc/services
- hostnamectl
- iptables
- apachectl


//


