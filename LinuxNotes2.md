# Linux/Bash-Notes [1]  - #!/bin/bash echo "skidrow;Linux-Notes!"

// Linux Course Notes //  - Skidrow  

// Linux Course // -  Exam 
================================================================================
1.1.1  -> System Managment  - 002 
// FHS //   - Every thing is a File (Linux) 
/root  - root user home dir
/boot  - bootloader and kernal files 
/etc   - etsy - everything else ( config files )
/opt   - addon software packages 
/media - removable media mount location
/mnt   - temp mount file system 
/tmp   - temp files deleted after reboot 
/sbin  - system binaries 
/bin   - other users can run 
/lib   - share libary files for /bin and /sbin 
/usr/bin  - user binary files
/usr/local - only for spefic computer 
/var       - file that change alot like log , web , mail , ftp 
/var/temp  - not deleted after reboot   
/dev       - hardware devices , com port , .. etc 
/proc      -device , kernal info  - every running process config on system 
/sys - info about devices , drivers ,kernal 
================================================================================
1.1.1 ->  Boot  003 
Hardware : PXE , USB , HARDDISK , CD/DVD/ , SSD  

- Bios - Uefi -> Grub2->vmlinux,z -> initrd(inintramdisk)->initramFS->FUllKernal 
- /boot  , efi , grub -/grub.cfg  -> /etc/defualt for edit boot config -> update-grub
================================================================================
1.1.3 Devices , Hardware information  004 
/dev 
sda -> SATA Drive 
nvme-> nvme Drives
C - Charcter 
B - Block 
/dev/null -> black hole to redirect stuff to 
lspci -> list of pci devices 
dmidecode -> info about keyworkds , bios , system .. etc 
free -h -> free memory 
================================================================================
1.1.4  Package  , Storage 005
Storage Concept - File , Block , Object 
Bios -> MBR (Master boot record ) , UEFUI (GUID)-GPT 
MBR - Old , 1 written section 
GPT - Newe, Writte across , has fake MBR so old devices know this one is GPT and not delete it 
\
Raid : - Raid[0] - Stripe => added togather , Total Size Combined - same file goes to all dirves [R,W] - Fast => loss of data if one drive fall 
       - Raid[1] - Mirrodd , 1  Size Of All  , No Speed , - Data is there even if one drive fails
       - Raid[5]   , -1   Size Of All  , No Speed , - More Secured => [ Can be recoverd ] 
================================================================================
1.2.1  Manage Files and dirs 006 
================================================================================
1.2.2 File Editing  007 
printf - 
- \n => new line
- \t => tab 
- %d => integer
- $f => float 
- %s => string
- sed '2'd -> delete d from line 2
- sed '2p' -> print line 2 
- sed -n '2p' -> only show line 2 nothing else 
- sed  's/yasser/skidrow/' -> replace word with a word 
- sed 's/#//'  -> remove all # comments from a file 
---------------
awk , -F sperated : , space .. etc  -> awk -F :  ' {print $1} ' 
================================================================================
1.2.4 - Archive and Comperssion 
cpio -> copy in /out  - files  cpio -o > , cpio -i <  
dd -> disk dump  - for devices - for disk images  dd if=input  of=output
tar -cf filename.tar - tar -xf filename.tar
gzip , bzip2 , xz 
gzip filename , gzip -K , bzip2 -K , xz -K  [ -K  Keep orignal file ]  - For Compress 
gzip -d filename or gunzip filename , bzip2 -d file , bunzip2 file , xz file  , unx file  - For decompress 
zip - archive & compress  , unzip  
================================================================================
1.2.5  Copy files over network 
- nc
- scp  - secure copy -> scp Host:path/file Destination    -r for folder and it's contents 
- rsync
================================================================================
1.3.1 - 011 - Disk Part , Monitor Storage Space 
- blkid 
- lsblk 
- fdisk 
- parted 
- dd if=/dev/zero of=/dev/drive count=100 -> delete a drive 
- partprobe => update kernal to read partion table 
- df (diskfree) = show block in use on mounted file system 
- du (diskusage) = files and dirs size used = how much space they take Storage 
================================================================================
1.3.3- 012 - LVM  
- LVM = Logical Volume Manager 
- PV's = Physical Volumes 
- VG's = Volume Group 
- LV's = Logical Volumes 
- lsblk
- pvcreate , pvdisplay 
- vgcreate , vgdisplay , vgextend 
- lvcreate , lvdisplay , lvextend 
================================================================================
1.3.3- 013 - MountingFS  
- /mnt
- mount device where
- umount device 
- /etc/fstab - to make mount on boot 
================================================================================
1.3.4- 014 - FileSystemManamgnet   
- mkfs.ext4
- dumpe2fs 
- e2fsck  , fsck 
- tune2fs  , resize2fs 
- xfs_admin 
- mdam  = raid 
- cat /proc/mdstat
================================================================================
1.3.5- 013 - SAN   
================================================================================
1.4.1 Systemctl 016 
- status , start , stop  , restart  , enable , disable , mask , unmask 
================================================================================
1.4.2 System Cronjobs 017
- at , crontab , crontab -e  , crontab -l 
================================================================================
1.4.3 Signal Kill 018 
SIGTERM  - kill -15 - Please Stop
SIGKILL  - kill -9  - Stop Now ( Force )  
SIGHUP   - kill -1  - ( iam leaving ) 
SIGINT   - kill -2  - (CTRL + C ) 
SIGUSR1  - kill -10 - ( Psst! Hi ) - by programmas and developers 
- pidof = get process id of a process  , pgrep 
- killall -9  = kill everything related to process 
- pkill -9 = kill process with name instead of pid 
================================================================================
1.4.4 process Managment 
-lsof = list open files 
- renice -n 0-19  PID
================================================================================
026  = 1.6.1 - Package Managment 
- rpm , dnf , yum , dpkg 
rpm -i -> for install 
dpkg -i -> for install 
yum install -> to install a package 
yum install -> to install a package
dnf history -> show history of dnf 
yum updste -> update packages 
dnf upgrade -> to upgrade package 
apt-get update , apt-get upgrade  , apt search , apt purge .. etc -> debian 
================================================================================
027 - Servcies , Configuration files 
/etc -> system wide services config 
systemctl restart service 
systemctl reload  service 
/etc/apt/sources.list -> get updates , upgrades 
/etc/apt/sources.list.d -> custom apps updates , upgrades 
/etc/apt/apt.conf.d -> config 
================================================================================
