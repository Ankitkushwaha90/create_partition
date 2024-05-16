### firt of all will be check how many your partition in system.
- so it's command is 
```bash
lsblk
```
- output
```bash
NAME         MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda            8:0    1  57.8G  0 disk 
├─sda1         8:1    1   4.1G  0 part 
├─sda2         8:2    1     1M  0 part 
├─sda3         8:3    1    33G  0 part 
└─sda4         8:4    1    19G  0 part 
nvme0n1      259:0    0 476.9G  0 disk 
├─nvme0n1p1  259:1    0    50M  0 part 
├─nvme0n1p2  259:2    0     1K  0 part 
├─nvme0n1p3  259:3    0   100M  0 part 
├─nvme0n1p4  259:4    0  17.6G  0 part /media/ankit/ec2578d4-a2a7-43f2-a21b-dbe7e8d77114
├─nvme0n1p5  259:5    0 293.1G  0 part /media/ankit/a1eb5b6f-ce4b-4c04-a658-a0a2dbecb4b7
├─nvme0n1p6  259:6    0  72.8G  0 part /media/ankit/F6A01704A016CACF
├─nvme0n1p7  259:7    0   768M  0 part 
├─nvme0n1p8  259:8    0   513M  0 part 
├─nvme0n1p9  259:9    0  33.2G  0 part /media/ankit/782a25c8-6d08-4866-853c-74987551f792
└─nvme0n1p10 259:10   0  58.9G  0 part /

```
### then we will be get select disk . which want to be create partition.
```bash
sudo fdisk /dev/sda
```
- output
```bash
Welcome to fdisk (util-linux 2.39.3).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.


Command (m for help): m

Help:

  DOS (MBR)
   a   toggle a bootable flag
   b   edit nested BSD disklabel
   c   toggle the dos compatibility flag

  Generic
   d   delete a partition
   F   list free unpartitioned space
   l   list known partition types
   n   add a new partition
   p   print the partition table
   t   change a partition type
   v   verify the partition table
   i   print information about a partition

  Misc
   m   print this menu
   u   change display/entry units
   x   extra functionality (experts only)

  Script
   I   load disk layout from sfdisk script file
   O   dump disk layout to sfdisk script file

  Save & Exit
   w   write table to disk and exit
   q   quit without saving changes

  Create a new label
   g   create a new empty GPT partition table
   G   create a new empty SGI (IRIX) partition table
   o   create a new empty MBR (DOS) partition table
   s   create a new empty Sun partition table

Command (m for help): p
Disk /dev/sda: 7.45 GiB, 8004304896 bytes, 15633408 sectors
Disk model: Cruzer Blade    
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x0004703b

Device     Boot    Start      End  Sectors  Size Id Type
/dev/sda1  *        2048 15631271 15629224  7.5G  7 HPFS/NTFS/exFAT
/dev/sda2       15631272 15633319     2048    1M ef EFI (FAT-12/16/32)

Command (m for help): n
      

```
- then press the defult enter , enter , then write +16G then enter
- then w
- then finish
- then create partition exectute for 
```bash
mkfs.ext4 /dev/sdb3
```
- then continue press enter enter and then wait ...
- Now successfully create your partition .
                  but is not create so we can need for change sinagure so, it's doing can be process all the data can be formate so carefully cange for pendrive sinature.
                      
        


