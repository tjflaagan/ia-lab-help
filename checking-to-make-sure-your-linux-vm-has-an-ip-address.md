# Basic Network Troubleshooting on Debian

Just follow the OSI Model!


### 1. Physical Connectivity
Check that your VM is connected to a network in the ialab. It should be.  
![image](https://user-images.githubusercontent.com/16710890/144479443-7106a857-ccb2-4ff1-b653-701327247848.png)

Check that your VM's NIC is link up using `ip link show` (stop using ifconfig, it's deprecated)  
![image](https://user-images.githubusercontent.com/16710890/144479726-c1d870af-9487-4fb2-8239-015a433f5d5b.png)

### 2. Data Link Layer
Ping something, then check your ARP table. Even if the ping drops, you should see the MAC address of the target or your gateway, anyway.  
![image](https://user-images.githubusercontent.com/16710890/144480502-29f9b6b2-3bed-4890-8b29-ca48523de6e2.png)

Try a layer 2 'ping' with `arping`:  
![image](https://user-images.githubusercontent.com/16710890/144480618-615dd34f-e37b-48e8-89c1-b6e3cfe030fb.png)

If these fail, double check VLAN settings, target host reachability (follow this guide for whatever you're trying to reach), restart the vApp, and so on.

### 3. Network Layer
Check your routes with `ip route`:  
![image](https://user-images.githubusercontent.com/16710890/144481308-89e8dc1a-a73c-4bf5-b117-c93853b3ee64.png)

Make sure the subnet that you expect to be on actually has a running DHCP server, if you're expecting a DHCP address. Use the [`dhcp-discover` nmap script](https://nmap.org/nsedoc/scripts/dhcp-discover.html).

Make sure that all users can use the network. Run `nmtui` as root, then edit the connection that should be working and make sure the checkbox is enabled:  
![image](https://user-images.githubusercontent.com/16710890/144482178-64552625-b7bb-4114-b753-c439c15a0261.png)

Make sure that if you should be using a static address, you have the right address, gateway, netmask, and so on.

### 4. The Rest
Let's say you need to use the internet. You can't load up the captive portal. First, troubleshoot DNS:  
- Ping an IP address outside your LAN to make sure any NAT is working
- Ping a domain name to make sure that DNS is working
  - If not, check your nameservers in `/etc/resolv.conf` - delete everything, then set it to the IALab DNS servers, your gateway, or CloudFlare (1.1.1.1). Now try again
- Open your browser of choice in private mode, so cookies and whatnot don't mess you up. Browse to https://captive.apple.com
- Still busted? Bother your instructor.

You need to reach a webpage, but it won't load.  
- First, try a ping or an arping. The host might not respond, but if this is an assignment it _probably_ will.
- Second, try opening the page in a private window so you don't have caching issues, or disable caching within dev tools:  
  ![disable caching in Firefox devtools](https://user-images.githubusercontent.com/16710890/144483409-84b215d2-7efc-463a-a949-2a992eb3f780.png)
- Third, use cURL to make sure your browser isn't just rendering a blank page or something:
  ![image](https://user-images.githubusercontent.com/16710890/144483831-7b174f48-eb61-4bae-9cc6-41c77656450d.png)
