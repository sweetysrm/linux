# linux

Kernel panic error troubshooting .


corrupted initrd file.
Corrupt root filesystem : If your root filesystem has changed locations recently, the initrd (or initramfs) file may be unable to locate them.
Initrd File Updates  orrupted initramfs.
kenel module is not compatiable 
 New Kernel,New Packages after Patching

Hardware failures 
--------------------
RAM Errors
disk Failures
logs to check 
----------------------
journalctl -k
dmesg
cat /var/log/syslog | grep -i ‘panic’
/var/log/kern.log

go to rescue mode 
 goto cd  /boot 
  ls -lrt
  corrupted/absent initramfs file.
  uname -r --check kernel version 
  regenerate initramfs with dracut or mkinitrd command:
  
  create new intramfs
  ------------------------
  dracut initramfs-3.10.0-1062.el7.x86_64.img 3.10.0-1062.el7.x86_64  ..rhel8
  mkinitrd initramfs-4.18.0-240.el8.x86_64.img 4.18.0-240.el8.x86_64 rhel7
  To replace exsiting initramfs file use:
  -------------------------------------------
  dracut -f initramfs-3.10.0-1062.el7.x86_64.img 3.10.0-1062.el7.x86_64
  mkinitrd --force initramfs-4.18.0-240.el8.x86_64.img 4.18.0-240.el8.x86_64
   reboot 
 
 if issue with kernel then need to downgrade kernel 
 --------------------------------------------------------
 
 go to sigle user mode 
 boot with previous kernel
 login to vm then unistall latest kernel and then reinstall the kernel.
 reboot 
