# Templetes and Snapshots

**Templetes:**    
    A vm templeate is a pre-configured image of a OS that can be used to deploy quickly.
    
 The VM deployement using templete uses two methods.
   1. Thin Method
   2. Clone method  

   **Thin clone mechanism** deploy the VM by using the templete image as base in read only mode and links an adintional diskto store newly generated data.
    -It require less diskspace, however, the VM will not work without the base image or templete image.
   
   **Clone mechanism** creates a complete new copy of the VMand it is fully independent of the base machine or VM templete.
     -It requires same disk space as original.   
