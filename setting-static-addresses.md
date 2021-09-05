# Setting Static Addresses

#### For any OS:

1. Make sure that you set the IP address, subnet mask, default gateway, and DNS if necessary

### For Windows:

1. Open the start menu, and type Run and open the Run dialog box.
2. Inside the Run dialog box, type `ncpa.cpl` and hit `OK`.
3. Right click on the interface you are changing and select properties.
4. Click Internet Protocol Version 4 in the window.
5. Click Properties.
6. Set the addresses appropriately and click OK.
![img](https://i.imgur.com/T3qAbMq.png)

### For Linux:

1. Can be done through NetPlan,
2. Navigate to /etc/netplan
3. Modify the default netplan configuration file in that directory with correct YAML syntax

#### OR

1. Network Manager
   1. This is the graphical user interface

## **NOTE**: AFTER changing an IP address, be sure to stop and start \(disable/re-enable\) the interface otherwise the change may not take affect.
