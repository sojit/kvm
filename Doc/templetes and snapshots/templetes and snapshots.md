# Templetes and Snapshots

**Templetes:**    
    A vm templeate is a pre-configured image of a OS that can be used to deploy quickly.
    
   **virt-sysprep** is a command utility provided by *libguestfs-tools* & it is used to remove the system specific configuration from the VM guest. So that clones can be made from it.
    
 The VM deployement using templete uses two methods.
   1. Thin Method
   2. Clone method  

**Thin mechanism** deploy the VM by using the templete image as base in read only mode and links an adintional diskto store newly generated data.
* It require less diskspace, however, the VM will not work without the base image or templete image.
* Example: Here is various details of using thin clone mechanism #kvm/Doc/templetes and snapshots/Thin_method.txt.
   
**Clone mechanism** creates a complete new copy of the VMand it is fully independent of the base machine or VM templete.
* It requires the same disk space as original.   


**Snapshots**
  A virtual machine snapshot is a file-based representation of a system state at a perticular point in time. It includes the Vm configuration and disk data.
>If in case any things goes wrong with the VM after the snapshot then we can revert to the VM previous state. Also, if the VM running any I/O intense applications then it advisable to take the snapshots after shutting down/suspend the guest machine.
      
The libvirt support live snapshot and the snapshorts are mainly two types:
1. Internal Snapshot
2. External Snapshot


