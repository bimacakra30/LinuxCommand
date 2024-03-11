# How To Up interface In Linux

  1. Install Nano / vim
  2. Edit File # nano /etc/network/interfaces
  3. Added new command at the bottom
     ```
     auto eth0
     iface eth0 inet dhcp
     ```
  5. Save

After configure, Reboot and check with ip -a or ifconfig
