#!/bin/bash

# Clear the screen
clear

# Optionally display the Introxt logo (if available)
[ -d Logo ] && [ -x Logo/introxt_logo ] && cd Logo && ./introxt_logo && cd ..

# Gather user input
read -p "Enter the interface: " int
read -p "Enter your IP address: " ip
read -p "Enter the starting IP address (e.g., 192.168.1.1): " start_ip
read -p "Enter the ending IP address: " end_ip

# Validate IP addresses
if [[ ! $start_ip =~ ^[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+$ || ! $end_ip =~ ^[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+$ ]]; then
    echo "Invalid IP address format."
    exit 1
fi

# Prepare output files
echo $int > alive_hosts.txt
echo $int > arping.txt

# Efficiently iterate through IP addresses
for ipaddr in $(seq $start_ip $end_ip); do
    arping -I $int -c 4 -s $ip $ipaddr >> arping.txt
    if [ $? -eq 0 ]; then
        echo $ipaddr
        arp $ipaddr >> alive_hosts.txt
    fi
done

# Display results
cat alive_hosts.txt
echo "Scan complete."
