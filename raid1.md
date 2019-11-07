# Raid1

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



