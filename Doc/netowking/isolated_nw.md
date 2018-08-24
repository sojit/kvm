

## Step1:

#cat ioslated.xml
<network> <name>isolated</name>
</network>

## Step2:

#virsh net-define ioslated.xml 
Network isolated defined from ioslated.xml

Vrifying the action performed on step2:
#cat /etc/libvirt/qemu/networks/isolated.xml

#virsh net-edit isolated
<network>
  <name>isolated</name>
  <uuid>83a3cc8a-7e57-4c3b-b4fc-0f7eaa40ccbb</uuid>
  <bridge name='virbr1' stp='on' delay='0'/>
  <mac address='52:54:00:9b:7a:be'/>
</network>

#virsh net-list --all
 Name                 State      Autostart     Persistent
----------------------------------------------------------
 default              active     yes           yes
 isolated             inactive   no            yes

## Step3:
#virsh net-start isolated 
Network isolated started

#virsh net-list --all
 Name                 State      Autostart     Persistent
----------------------------------------------------------
 default              active     yes           yes
 isolated             active     no            yes

#brctl show
bridge name	bridge id		STP enabled	interfaces
br1		8000.525400bf745b	no		eth1
virbr0		8000.525400f1aacb	yes		virbr0-nic
virbr1		8000.5254009b7abe	yes		virbr1-nic
