	#kvm #linux #virtualization
virsh list --all //list vm running

  
Virsh commands

  

virsh domiflist vmname // get mac address

virsh domblklist vmname // get vm file location

virsh dominfo vmName

virsh autostart vmName;  

virsh suspend vmName;

  virsh shutdown vmName;

virsh resume vmName;

virsh shutdown rockylinux9 && virsh start rockylinux9 // restart machine
  

virsh destroy vmName && virsh undefine vmName && rm -f /var/lib/libvirt/images/ubuntu2004.qcow2 //remove vm and remove qcow2 file

---

virsh shutdown ubuntu22Inst2 && virt-edit /media/part1disk1/ubuntu22Inst2.qcow /etc/netplan/00-installer-config.yaml  //edit file in vm

virsh edit ubuntu22Inst2 // edit vm config in text editor (shutdown machine before and than start after finishing editing)

import image

```
sudo virt-install --virt-type=kvm --name=ubuntu22Inst2 --ram=4048 --vcpus=2 --os-variant=ubuntu20.04 --virt-type=kvm --hvm --network type=direct,mac=02:00:00:e0:a1:94,source=eno3,source_mode=bridge,model=rtl8139,address.type=pci,address.domain=0,address.bus=0,address.slot=9,address.function=0 --graphics vnc --disk path=/media/part1disk1/ubuntu22Inst2.qcow --import --noautoconsole
```

install from image

```
sudo virt-install --virt-type=kvm --name=ubuntu22 --ram=8048 --vcpus=6 --os-variant=ubuntu18.04 --virt-type=kvm --hvm --cdrom=/var/lib/libvirt/images/ubuntu-22.04-live-server-amd64.iso --network type=direct,mac=02:00:00:36:bf:3d,source=eno3,source_mode=bridge,model=rtl8139,address.type=pci,address.domain=0,address.bus=0,address.slot=9,address.function=0 --graphics vnc --disk path=/media/part1disk1/ubuntu22.qcow2,size=60,bus=virtio,format=qcow2
```

[1]: https://docs.ovh.com/us/en/dedicated/network-bridging/