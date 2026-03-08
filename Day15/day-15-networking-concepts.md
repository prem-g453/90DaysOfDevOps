#### Day 15 – Networking Concepts: DNS, IP, Subnets \& Ports

##### 

##### Task 1: DNS – How Names Become IPs



What happens when you type google.com in a browser?



When a user types google.com in a browser, the system first checks its local DNS cache for the IP address. If it is not found, the request goes to a DNS resolver, which queries DNS servers (root → TLD → authoritative server) to find the IP address for the domain. Once the IP address is found, it is returned to the browser. The browser then uses that IP address to connect to Google's server and load the website.



DNS Record Types



A Record – Maps a domain name to an IPv4 address.

AAAA Record – Maps a domain name to an IPv6 address.

CNAME Record – Points one domain name to another domain name.

MX Record – Specifies the mail server responsible for receiving emails for a domain.

NS Record – Specifies the authoritative name servers for a domain.



Command

dig google.com



Example output section:



google.com.     300     IN      A       142.250.183.14



A Record IP: 142.250.183.14

TTL: 300



##### Task 2: IP Addressing



What is an IPv4 Address?



An IPv4 address is a 32-bit numerical identifier used to identify devices on a network. It is written in dotted decimal format such as 192.168.1.10, consisting of four numbers (0–255) separated by dots.



Public vs Private IP



Public IP – Accessible over the internet and assigned by ISPs.

Example: 8.8.8.8



Private IP – Used inside local networks and not accessible directly from the internet.

Example: 192.168.1.10



Private IP Ranges

10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255

Command

ip addr show



Example private IP identified:



inet 192.168.1.20/24



This is a private IP address.



##### Task 3: CIDR \& Subnetting



What does /24 mean in 192.168.1.0/24?



The /24 represents the number of bits used for the network portion of the IP address. In this case, the first 24 bits are for the network and the remaining 8 bits are for hosts.



Usable Hosts



/24 → 254 usable hosts



/16 → 65,534 usable hosts



/28 → 14 usable hosts



Why Do We Subnet?



Subnetting divides a large network into smaller networks. This improves network organization, increases security, and reduces broadcast traffic.



CIDR Table

CIDR	Subnet Mask	Total IPs	Usable Hosts

/24	255.255.255.0	256	254

/16	255.255.0.0	65,536	65,534

/28	255.255.255.240	16	14

##### 

##### Task 4: Ports – The Doors to Services



What is a Port?



A port is a communication endpoint used by applications to send and receive data over a network. Ports allow multiple services to run on the same IP address.



Common Ports

Port	Service

22	SSH

80	HTTP

443	HTTPS

53	DNS

3306	MySQL

6379	Redis

27017	MongoDB

Command

ss -tulpn



Example output:



tcp   LISTEN 0      128     0.0.0.0:22        0.0.0.0:\*    users:(("sshd",pid=900))

tcp   LISTEN 0      128     127.0.0.1:3306    0.0.0.0:\*    users:(("mysqld",pid=1200))



Matched services:



Port 22 → SSH



Port 3306 → MySQL



##### Task 5: Putting It Together

curl http://myapp.com:8080

&nbsp;— What concepts are involved?



When running this command, DNS resolves myapp.com to an IP address. The request then connects to that IP using HTTP over port 8080. Networking concepts involved include DNS resolution, IP addressing, and port communication.



Your app can't reach database at 10.0.1.50:3306 — What would you check first?



First check if the database server is reachable using ping or telnet. Then verify that port 3306 is open and the database service is running. Also confirm firewall rules and network connectivity between the application and database.



##### What I Learned



DNS converts human-readable domain names into IP addresses so computers can communicate.



CIDR notation helps define network size and determine the number of available hosts.



Ports allow multiple services like HTTP, SSH, and databases to run on the same machine.



##### Commands Used



dig google.com

ip addr show

ss -tulpn

Git Steps

git add 2026/day-15/day-15-networking-concepts.md

git commit -m "Day 15 - Networking concepts: DNS, IP, CIDR and Ports"

git push origin main

