# ARPHawk
**Overview**
This script expedites network discovery by leveraging ARP requests to efficiently identify active hosts across an IP range, ideal for rapid network mapping and device inventory.

**Features**
* Rapid ARP scanning of IP addresses within a specified range.
* Clear and user-friendly interface for input and output.
* Logging of ARP results for further analysis.
* Optional display of an Introxt logo (if available).

**Usage**

```bash
git clone https://github.com/giruu/ARPHawk.git
```
Navigate to the cloned directory:

```bash
cd ARPHawk
```

Make the script executable: 
```bash
chmod +x ARPHawk.sh
```

Run the script: 
```bash
./ARPHawk.sh
```
Follow the prompts to enter the interface, your IP address, and the IP range.

**Dependencies**
arping command (install with sudo apt-get install arping on Debian-based systems)

**Technical Details**
* ARP (Address Resolution Protocol): Used to discover the MAC addresses of devices on a local network.
* arping command: Sends ARP requests and receives replies to identify active hosts.
* seq command: Generates a sequence of IP addresses for efficient iteration.

**Output files:**
arping.txt: Logs detailed ARP results for each scanned IP.
alive_hosts.txt: Lists the IP addresses of discovered active hosts.

**Notes**
Adjust the arping parameters if needed for your specific network environment.
The script optionally displays a logo if the "Logo" subdirectory and "introxt_logo" file are present.
