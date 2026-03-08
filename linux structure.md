
![[Screenshot 2026-03-04 232652.png]]


| Directory     | Purpose                                                                            |
| ------------- | ---------------------------------------------------------------------------------- |
| /             | Root directory. The top-level of the system. Everything starts from here.          |
| /bin          | Essential system programs (e.g., ls, cp, mv). Used by all users.                   |
| /sbin         | System administration programs (e.g., iptables, reboot). Mostly for root user.     |
| /usr/bin      | Extra programs installed (e.g., nmap, hydra). Regular users can use them.          |
| /usr/sbin     | Extra third party system admin tools (e.g., apache2, mysql). Mostly for root user. |
| /etc          | Configuration files for the system and applications (e.g., passwd, shadow).        |
| /home         | Personal files for each user (e.g., /home/user/).                                  |
| /root         | Home directory of the root (admin) user.                                           |
| /tmp          | Temporary files. Deleted automatically after reboot.                               |
| /var          | Stores logs, cache, and databases (e.g., /var/log, /var/lib).                      |
| /opt          | Third-party software (e.g., extra tools like Burp Suite).                          |
| /boot         | Boot files like the Linux kernel and GRUB bootloader.                              |
| /dev          | Contains device files (e.g., sda for hard drives, tty for terminals).              |
| /mnt          | Mount point for external drives (e.g., USB, network drives).                       |
| /media        | Auto-mounting for USB and CD/DVD drives.                                           |
| /proc         | Virtual system info files (e.g., CPU, memory usage).                               |
| /sys          | Another virtual system folder. Used by the kernel to manage hardware.              |
| /lib & /lib64 | System libraries needed for running programs.                                      |
*[]()*