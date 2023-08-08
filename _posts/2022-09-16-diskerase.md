---
layout: post
title: "Easily Restore Your USB Drive with fdisk in Linux"
date: 2022-09-16 12:50:00 +0300
background: '/img/ps-03.jpg'
---

If you're anything like me, you love experimenting with various Linux distributions. However, constantly creating bootable live USB drives for different distros can leave you with a cluttered and confusing USB drive. To avoid this mess and restore your USB drive to its original state, I've got a simple solution for you using fdisk in Linux.

Let's dive into the step-by-step process to wipe all partitions and restore your USB drive, thanks to a helpful tip from PenDriveLinux.com.

**Note: Before proceeding, ensure you've backed up any important data on the USB drive, as the following steps will completely erase its contents.**

### Step 1: Delete Old Partitions

1. Open a terminal and gain root access by typing:
   ```bash
   sudo su
   ```

2. Identify your USB drive letter using fdisk:
   ```bash
   fdisk -l
   ```

3. Once you've identified the drive letter (let's call it /dev/sdx), use fdisk to work with the USB drive:
   ```bash
   fdisk /dev/sdx
   ```

4. Type `d` to delete a partition.

5. Type `1` to select the 1st partition and press Enter.

6. Type `d` again to delete another partition. Don't worry; fdisk should automatically select the second partition.

### Step 2: Create the New Partition

7. To create a new partition, type `n`.

8. Next, make this partition primary by typing `p` and press Enter.

9. Type `1` to make this the first partition, and then press Enter.

10. Press Enter twice to accept the default first and last cylinder.

11. Write the new partition information to the USB drive by typing `w`.

12. Unmount the USB drive by typing:
    ```bash
    umount /dev/sdx
    ```

### Step 3: Create the FAT Filesystem

13. Finally, create a FAT 32 filesystem on the new partition by typing:
    ```bash
    mkfs.vfat -F 32 /dev/sdx1
    ```

And there you have it! Your USB drive is now restored to a single FAT 32 partition, ready to be read from any computer.