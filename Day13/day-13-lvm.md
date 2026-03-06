#### Day 13 – Linux Volume Management (LVM)

Objective



Learn how to manage storage using LVM (Logical Volume Manager) by creating physical volumes, volume groups, logical volumes, and extending storage.



##### Task 1 – Check Current Storage

Commands Used

lsblk

pvs

vgs

lvs

df -h

Description



These commands help check the current disk structure and LVM configuration.



lsblk → Shows block devices



pvs → Displays physical volumes



vgs → Displays volume groups



lvs → Displays logical volumes



df -h → Shows mounted disk usage





##### Task 2 – Create Physical Volume



Command

pvcreate /dev/sdb



If using a virtual disk:



pvcreate /dev/loop0

Verify

pvs

Description



A Physical Volume (PV) is the raw disk or partition used by LVM.





##### Task 3 – Create Volume Group



Command

vgcreate devops-vg /dev/sdb

Verify

vgs

Description



A Volume Group (VG) is a pool of storage created from one or more physical volumes.



##### Task 4 – Create Logical Volume



Command

lvcreate -L 500M -n app-data devops-vg

Verify

lvs

Description



A Logical Volume (LV) is the usable storage created from the volume group.



##### Task 5 – Format and Mount Logical Volume



Format the Volume

mkfs.ext4 /dev/devops-vg/app-data

Create Mount Directory

mkdir -p /mnt/app-data

Mount the Volume

mount /dev/devops-vg/app-data /mnt/app-data

Verify

df -h /mnt/app-data

Output Screenshot





##### Task 6 – Extend Logical Volume



Extend the Volume

lvextend -L +200M /dev/devops-vg/app-data

Resize Filesystem

resize2fs /dev/devops-vg/app-data

Verify

df -h /mnt/app-data

Output Screenshot



What I Learned



LVM allows flexible disk management, unlike traditional partitions.



Storage can be extended without unmounting disks in many cases.



Logical volumes can be resized dynamically as storage needs grow.



Commands Summary

lsblk

pvs

vgs

lvs

df -h

pvcreate /dev/sdb

vgcreate devops-vg /dev/sdb

lvcreate -L 500M -n app-data devops-vg

mkfs.ext4 /dev/devops-vg/app-data

mkdir -p /mnt/app-data

mount /dev/devops-vg/app-data /mnt/app-data

lvextend -L +200M /dev/devops-vg/app-data

resize2fs /dev/devops-vg/app-data

Conclusion



Today I learned how to manage storage using Linux LVM, including creating physical volumes, volume groups, logical volumes, and extending storage dynamically.

