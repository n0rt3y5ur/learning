# Gns3
Despliegues de labs con gvd.

GV: gnse3 + virtualization

Film: Hackers

Some related labs: 
+ dvwa - Damn Vulnerable Web App (https://github.com/digininja/DVWA) 
+ vulnhub (directory with machines with labs) https://www.vulnhub.com/
+ OWASP Juice Shop https://owasp.org/www-project-juice-shop/

## Type of attacks you can reproduce by using GNS3:
+ Taking over the root bridge
+ Simulation a dual-homed switch 
+ DHCP Spoofing
+ VLAN hopping attackes ARP attacks
+ BGP attacks
+ Layer 2 Port Authentification
+ SIP attacks

Search for the differences between VM and docker, related to the concept Contenerización

Research these architectures: Qemu x86, x86_64, arm, mips, aparc, ppc...

Qemu is used for emulation purposes. 

GNS3 - Graphical Network Simulators 

## Several ways to make it work
+ On your computer: local server + client
+ Client on your computer and server on the VM in virtualbox.
+ Client on a remote server + Server on a remote server
+ Client on a remote server + Server on a remote server
+ Other... (topologies)

## Components:
uBridge Nodes interconection with tunnels, 
Qemu Emulation software
VPDCs emulates a computer with a basic network configuration
Docker
IOU Cisco emulator
Dynamics
NAT y Cloud (need libvirt)
VNC Viewer
Wireshark.

CTRL + Shift + P -> Preferences. Where all settings.

In this environment, we can add our own devices. For instance, cisco routers. There is a place to download the firmware that allows you to replicate.

Search for the concept: port mirrowing applied to a switch.

## Switching
C3725 rooter - NM-16ESW (256Mb).

Search for vboxmanage to create/modify/eliminate networks for virtualbox from the terminal.


# GNS3 Appliances 
You can get it from the gns3 marketplace

Next steps
+ Ostinato. Software to sobrecargar la red.
+ NETem
+ Network automation Unetmiko, napalm, pyntc and ansible).


## To download images
dockerhub, turnkey, tfr.org telectronica (for cisco).

## Alternatives to GNS3 
+ unetlab (deprecated)
+ Eve-ng 
+ Virl (Cisco Virtual Internet Routing Lab)
+ eNSP (huawei)
 
A good thing is that you can mount a lab with cisco plus huawei.



