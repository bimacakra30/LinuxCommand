# How to fix "can not open access to console the root account is locked"

I recently experienced this problem, but I only had answers that did not help. Then, I was able to get a hint from the short opinion of the Linux Forum.

This problem is related to the change of the drive. If it is not properly reflected in `/etc/fstab`, such an error may occur.

  1. Download SystemRescueCD and make a bootdisk: https://www.system-rescue.org/

  2. FDISK and MOUNT
  
      ```bash
      # fdisk -l    # find a drive
      # mkdir /mnt/tmp
      # mount -t ext4 /dev/sda2 /mnt/tmp    # mount -t [filesystem] [drive] [mountpoint]
      ```

   3. Open the `[mountpoint]/etc/fstab` in text editor, and remove lines of the detacted devices
   4. mount -o remount,rw /
   5. Save and reboot, and remove the bootdisk.

Done.
