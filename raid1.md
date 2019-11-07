# Raid1

link [http://itfound.ru/57-ubuntu-raid1.html](http://itfound.ru/57-ubuntu-raid1.html)

пакет $ apt-get install mdadm

вдруг есть райд

$ cat /proc/mdstat

sudo umount /dev/md0

sudo mdadm --stop /dev/md0

sudo mdadm --remove /dev/md0

посмотреть устройства 

lsblk -o NAME,SIZE,FSTYPE,TYPE,MOUNTPOINT

обнулить массивы

$ sudo mdadm --zero-superblock /dev/sdc

$ sudo mdadm --zero-superblock /dev/sdd

проверить конф sudo nano /etc/mdadm/mdadm.conf

СОЗДАНИЕ

$ sudo mdadm --create --verbose /dev/md0 --level=1 --raid-devices=2 /dev/sda /dev/sdb

created yes

$ cat /proc/mdstat

$ sudo mkfs.ext4 -F /dev/md0

mounts 

$ sudo mkdir -p /mnt/md0 $ sudo mount /dev/md0 /mnt/md0 

VIEW 

df -h -x devtmpfs -x tmpfs

SAVE 

$ sudo mdadm --detail --scan \| sudo tee -a /etc/mdadm/mdadm.conf $ sudo update-initramfs -u

FSTAB 

$echo '/dev/md0 /mnt/md0 ext4 defaults,nofail,discard 0 0' \| sudo tee -a /etc/fstab



