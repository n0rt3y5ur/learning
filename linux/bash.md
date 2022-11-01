# Bash Cheat Sheet

## du
Display files and their size. To display all files in current folder:
```
du -sh *
```

## lsblk
Lists information about all available or the specified block devices.
```
lsblk -fa
```

**Flags**
+ -f : Output  info about filesystems
+ -a : Also list empty devices and RAM disk devices.

## lspci
Shows all devices currently connected to the PCI (Peripherical Component Interconnect) bus. PCI devices can be either a component attached to the motherboard, like a disk controller, or an expansion card fitted into a PCI slot, like an internal graphics card.
```
lspci
```
To see an specific device:
```
lspci -s 00:00.0 -v
```

**Flags**
+ -s : allows to choose a device. In the example 00:00.0 is the device id.
+ -v : shows general information. v stands for verbose.
+ -k : shows kernel drivers.


## lsusb
Lists USB (Universal Serial Bus) devices currently connected to the machine. 
```
lsusb
```
A specific device can be selected for inspection by providing ID to the option -d:
```
lsusb -v -d 1701:099e
```

**Flags**
+ -d : allows to choose a device. In the example 1701:099e is the device id.
+ -v : shows detailed input. v stands for verbose.
+ -t : shos the current USV mapping as a hierarchical tree.




## rpm

```
rpm -qc <package-name>
```

**Flags**
+ -q : query
+ -a : all
+ -c : configuration file

## dpkg
Install a deb package
```
sudo dpkg -i <packageName.deb>
```

####
https://geekland.eu/reparar-paquetes-rotos-linux/
