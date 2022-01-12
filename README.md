# S19_root_hack
Exploit for the Bitmain S19 miner to get root.

# How to hack the Antminer S19 Pro.

Copy the archive file over to the device, login, then run the following commands.

user@kali $: cat s19_pro_root.tar|ssh miner@192.168.2.95 "cat >/tmp/s19_pro_root.tar"

user@kali $: ssh miner@192.168.2.95

Password: miner

miner@S19PRO-01$ ~ cd /tmp/

miner@S19PRO-01$ /tmp tar -xf s19_pro_root.tar

miner@S19PRO-01$ /tmp chmod +x *.sh

miner@S19PRO-01$ /tmp /tmp/ownit.sh

# Some security worthy notes:
- SSH server is running with root login disabled. (/usr/sbin/dropbear -R -w)
- Sudoers file has restrictive permissions and only a small list of commands are enabled.
- /etc/passwd entry for the root user has a shell of /bin/false. Needed to change to /bin/sh. 
- The root user password is "admin". The miner user password is "miner".
- busybox is very stripped down. Uploaded a better one to get access to 'su' and better tools.

