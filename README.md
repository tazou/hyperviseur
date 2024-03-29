# Hyperviseur Libre sous Linux

# Prérequis

## Dépendances 
 - sudo apt install qemu-kvm bridge-utils qemu-utils libvirt-daemon-system libvirt-clients virtinst netcat-openbsd
 - sudo apt install virt-manager #(Le client graphique)
 - sudo systemctl restart libvirtd
 - sudo cp qemu-ifup /etc/

## Mise en place du bridge 
 - sudo brctl addbr br0

Dans le fichier /etc/network/interfaces
```
auto br0
  iface br0 inet dhcp
  bridge_ports enp0s31f6
```

## Manipuler les VM 
 - virsh list --all
 - virsh start <vm-name>
 - virsh shutdown <vm-name>
 - virsh destroy <vm-name>
 - virsh edit <vm-name>

## Se connecter en graphique sur une VM 
 - xtightvncviewer localhost

## Notes
 - https://ahelpme.com/linux/howto-do-qemu-full-virtualization-with-bridged-networking/
 - https://wiki.qemu.org/Documentation/Networking
