#### Day 14 – Networking Fundamentals \& Hands-on Checks



Quick Concepts



##### OSI vs TCP/IP Model



OSI Model (7 Layers)



Physical – cables, signals, hardware transmission



Data Link – MAC address communication (Ethernet)



Network – IP addressing and routing



Transport – TCP/UDP communication between hosts



Session – manages sessions between applications



Presentation – encryption, formatting, compression



Application – user-facing services (HTTP, DNS, FTP)



TCP/IP Model (4 Layers)



Link – physical + data link communication



Internet – IP addressing and routing



Transport – TCP/UDP data transport



Application – HTTP, DNS, SMTP, etc.



Where Common Protocols Sit



IP → Internet layer



TCP / UDP → Transport layer



DNS → Application layer



HTTP / HTTPS → Application layer



Real Example



Example request:



curl https://example.com



Flow of layers:



Application → HTTP/HTTPS

Transport → TCP

Internet → IP

Link → Network interface (Ethernet/WiFi)



So the request travels as:



HTTP over TCP over IP



Hands-on Checks



Target host used: google.com



##### 1\. Identity



Command:



hostname -I



Output:



192.168.1.12



Observation:

This shows my system's local IP address on the network.



##### 2\. Reachability



Command:



ping google.com



Output (example):



64 bytes from 142.250.193.14: icmp\_seq=1 ttl=115 time=20 ms



Observation:



Latency around 20 ms



No packet loss



Host is reachable



##### 3\. Path to Target



Command:



traceroute google.com



Observation:



Shows multiple hops between my system and Google servers



First hops are local ISP routers



Later hops are Google network infrastructure



##### 4\. Open Ports \& Services



Command:



ss -tulpn



Example output:



tcp LISTEN 0 128 0.0.0.0:22



Observation:



Port 22 is listening



Service running: SSH



##### 5\. Name Resolution



Command:



nslookup google.com



Output:



Name: google.com

Address: 142.250.193.14



Observation:



DNS successfully resolves google.com → IP address



##### 6\. HTTP Check



Command:



curl -I https://google.com



Output:



HTTP/2 200



Observation:



Status code 200 OK



Website is responding correctly



##### 7\. Connections Snapshot



Command:



netstat -an | head



Observation:



Several LISTEN ports available



Some ESTABLISHED connections to external services



Mini Task – Port Probe



Listening port identified:



22 (SSH)



Test command:



nc -zv localhost 22



Output:



Connection to localhost 22 port \[tcp/ssh] succeeded!



Observation:



SSH port is reachable locally.



If it was unreachable, next checks would be:



Check service status



Verify firewall rules



Confirm port configuration



Reflection

1\. Fastest command when something is broken



ping



It quickly tells whether the host is reachable and shows latency.



2\. If DNS fails, which layer to inspect?



Application Layer (DNS service).



Possible checks:



/etc/resolv.conf



DNS server connectivity



DNS configuration



3\. If HTTP 500 error appears?



Application layer issue.



Possible causes:



Server-side application failure



Web server configuration issue



Backend service error



4\. Two follow-up checks in a real incident



Check open ports



ss -tulpn



Check service response



curl -I http://service-url

Commands Practiced



hostname



ping



traceroute



ss



nslookup



curl



netstat



nc



