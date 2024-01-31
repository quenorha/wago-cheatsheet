# WAGO Cheat Sheet
Useful command line for WAGO devices

## Debug

* Display kernel version information :
```
uname -a
```
* Display firmware version :
```
cat /etc/REVISIONS
```
* List running processes :
```
ps -A
```
* Open an interactive process viewer (with ressources) :
```
htop
```

* List processes using the file :
```
lsof myfile //where myfile is the filename
```
* List files used by a process
```
lsof –p 3255 //where 3255 is the process number
```
* Count all files opened
```
lsof | wc -l
```
* List all IP sockets
```
lsof -i
```
* List all files opened by a process
```
ls -l /proc/3255/fd/
```
* List all TCP connections
```
netstat -tap
```
* List all UDP connections
```
netstat -udp
```
* List all open ports with associated processes
```
netstat -tulpn | grep LISTEN
```
* Display total and used space on file system
```
df –h
```
* Display all messages from the kernel ring buffer
```
dmesg
```
* Capture and display network traffic on interface br0
```
tcpdump -i br0
```
* Capture and display network traffic on interface br0 in ASCII format
```
tcpdump -i br0 -A
```
* Capture and display network traffic on interface br0 in HEX format
```
tcpdump -i br0 -XX
```
* Capture network traffic on interface br0 and save it to .pcap file (can be open with Wireshark)
```
tcpdump -w capture.pcap -i br0
```
* Open .pcap file and display content
```
tcpdump -r capture.pcap 
```
* Capture and display TCP packets on interface br0 
```
tcpdump -i br0 tcp
```
* Capture and display traffic on interface br0 with specific port
```
tcpdump -i br0 port 502
```
* Capture and display traffic on interface br0 with specific source ip address
```
tcpdump -i br0 src 192.168.0.2
```
* Capture and display traffic on interface br0 with specific destination ip address
```
tcpdump -i br0 dst 192.168.0.44
```

## Package manager

* Install a package
```
opkg install package.ipk
```

* Install a package in debug mode
```
opkg install -V3 package.ipk
```

* Remove a package
```
opkg remove package
```

* Remove a package in debug mode
```
opkg remove -V3 package
```

* List installed packages
```
opkg list_installed
```

* Display information about a package
```
opkg info package
```
