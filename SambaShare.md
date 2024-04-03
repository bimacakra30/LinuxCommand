# How To Install and Setup Samba Share
  1. Before following this step, login to superuser then Update repository
     ```
     apt update
     ```
  3. Install Samba
     ```
     apt install samba -y
     ```
  4. Start samba
     ```
     systemctl start smbd nmbd
     systemctl enable smbd nmbd
     ```
  5. Edit samba configuration
     ```
     nano /etc/samba/smb.conf
     ```
  6. Add new Private for samba
     ```
     [Private]
     comment = private share
     path = /data/private/
     browseable = yes
     guest ok = no
     writable = yes
     valid users = @samba
     ```
  7. Add new user for samba, Example user bara
     ```
     adduser bara
     ```
  8. Create password for samba user
     ```
     smbpasswd -a bara
     ```
  9. Create new samba group
     ```
     groupadd samba
     ```
     gpasswd -a bara samba
     ```
  10. Create a shared folder that you have specified in the smb.conf file
      ```
      mkdir -p /data/private
      ```
  11. Provide read and write permissions to the Samba share
      ```
      setfacl -R -m "g:samba:rwx" /data/private
      ```
  12. Finish, To connect to samba server using [ip_server]
