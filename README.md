Frogger2.1 - VLAN Hopping
============================================

Simple VLAN enumeration and hopping script.


Developed by Daniel Compton

https://github.com/commonexploits/vlan-hopping

Released under AGPL see LICENSE for more information


Installing  
=======================
 git clone https://github.com/3tternp/vlan-hopping

Installing   requirements 
=======================
 cd vlan-hopping
 
 sudo bash requirements.sh
 
How To Use	
=======================
 ./frogger2.sh

Run as root.

Features	
=======================

* Sniffs out CDP packets and extracts (VTP domain name, VLAN management address, Native VLAN ID and IOS version of Cisco devices)
* It will enable a DTP trunk attack automatically
* Sniffs out and extracts all 802.1Q tagged VLAN packets within STP packets and extracts the unique IDs.
* Auto arp-scans the discovered VLAN IDs and auto tags packets and scans each VLAN ID for live devices.
* Auto option to auto create a VLAN interface within the found network to connect to that VLAN.
* Added SNMP VLAN informaion extraction
* Added SNMP VLAN Hopping
* Added DTP Scan - Passively detect DTP modes and VLAN hopping possibility
* Added CDP info extraction


Requirements   
=======================
* arp-scan (built into kali linux)
* Yersina (built into kali linux)
* Tshark (built into kali linux)
* Screen (built into kali linux)
* Vconfig (built into kali linux) 

Tested on Kali 2023.2. All dependencies will be checked for when running.

* Notes for VMware. VLAN hopping generally (not just this script) can have issues within VMware if running the VM within Windows with certain Intel drivers. The Intel drivers strip off the tags before it reaches the VM. Either use an external USB ethernet card such as a DLink USB 2.0 DUB-E100 (old model 10/100 not gigabit) or boot into Backtrack nativiely from a USB stick. Intel has published a registry fix, to work on some models: http://www.intel.com/support/network/sb/CS-005897.htm - adding "MonitorMode" 1 to the registry does resolve the issue.


Screen Shot    
=======================
<img src="http://www.commonexploits.com/images/frogger2.png" alt="Screenshot" style="max-width:100%;">


Change Log
=======================
* version 2.1 - 11/07/23 - minor changes are made as per the requirements of kali linux 2023.2 
* Version 2.0 - 14/09/16 - 44CON Release. Info/Help to publish soon. Added DTPScan, SNMP Hopping. Many improvements.
* Version 1.8 - Added VMware detection and Intel NIC detection to assist with common problems within VMware.
* Version 1.7 - New look, bug fixes and speed improvements.
* Version 1.5 - Official release.
