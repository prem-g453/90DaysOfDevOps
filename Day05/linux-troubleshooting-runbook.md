#### Day 05 – Linux Troubleshooting Drill



Target Service

docker.service



Process

dockerd

##### 

##### Environment Check



Command

uname -a



Observed

Ubuntu system running on x86\_64

Kernel version confirmed



Command

cat /etc/os-release



Observed

Ubuntu 22.04 LTS

##### 

##### Filesystem Check



Command

mkdir /tmp/runbook-demo

cp /etc/hosts /tmp/runbook-demo/hosts-copy

ls -l /tmp/runbook-demo



Observed

Folder created

File copied

No permission issues



Command

df -h



Observed

Disk usage normal

No storage issue



##### CPU and Memory



Command

ps -eo pid,pcpu,pmem,comm | grep dockerd



Observed

Low CPU usage

Memory usage normal



Command

free -h



Observed

Enough free memory

No swap pressure



##### Network



Command

ss -tulpn | grep docker



Observed

Docker listening on expected port



Command

curl -I http://localhost



Observed

HTTP 200 response

Service reachable



Logs



Command

journalctl -u docker -n 50



Observed

No recent errors

Service running normally



##### Quick Finding



Docker service healthy

System resources stable

No errors found



If Issue Increases



Restart service

sudo systemctl restart docker



Check container logs

docker logs container\_id



Check resource usage

docker stats

