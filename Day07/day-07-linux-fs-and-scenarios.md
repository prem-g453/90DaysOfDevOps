#### Day 07 – Linux File System Hierarchy \& Scenario Practice





##### Part 1 – Linux File System Hierarchy

/



Root directory

Starting point of everything in Linux

All directories exist under this



Command

ls -l /



I saw folders like bin, etc, home, var



I would use this when navigating from top level of system



/home



Contains home directories of normal users



Command

ls -l /home



I saw user folders



I would use this when checking user files and scripts



/root



Home directory of root user



Command

ls -l /root



Contains root specific files



I would use this when logged in as root



/etc



Stores system configuration files



Command

ls -l /etc



Saw hostname, hosts, passwd, ssh



Command

cat /etc/hostname



I would use this when changing system configuration



/var/log



Contains log files

Very important for DevOps



Command

ls -l /var/log



Saw syslog, auth.log, journal



Find largest logs

du -sh /var/log/\* 2>/dev/null | sort -h | tail -5



I would use this when troubleshooting service failures



/tmp



Stores temporary files

Usually cleared after reboot



Command

ls -l /tmp



I would use this when checking temporary script outputs



/bin



Contains essential system commands like ls, cp, mv



Command

ls -l /bin



I would use this to understand where core binaries are stored



/usr/bin



Contains user level commands like git, python, nano



Command

ls -l /usr/bin



I would use this when verifying installed applications



/opt



Contains optional or third party software



Command

ls -l /opt



I would use this when installing custom applications



Check home directory



ls -la ~

##### 

##### Part 2 – Scenario Based Practice

Scenario 1 – Service Not Starting



Service myapp failed after reboot



Step 1

systemctl status myapp

Why: Check if service is running or failed



Step 2

journalctl -u myapp -n 50

Why: Check last 50 log lines



Step 3

systemctl is-enabled myapp

Why: Check if service starts on boot



Step 4

systemctl list-units --type=service

Why: Confirm service exists



Learning

Always check status first, then logs, then boot configuration



Scenario 2 – High CPU Usage



Server is slow



Step 1

top

Why: Shows live CPU usage



Step 2

ps aux --sort=-%cpu | head -10

Why: Show top CPU consuming processes



Step 3

Note PID of highest process



Learning

Identify process before killing anything



Scenario 3 – Finding Service Logs



Check docker logs



Step 1

systemctl status docker

Why: Confirm service status



Step 2

journalctl -u docker -n 50

Why: View recent logs



Step 3

journalctl -u docker -f

Why: Follow logs in real time



Learning

Systemd services store logs in journald



Scenario 4 – Permission Denied



backup.sh not executing



Step 1

ls -l /home/user/backup.sh

Why: Check permissions



Step 2

chmod +x /home/user/backup.sh

Why: Add execute permission



Step 3

ls -l /home/user/backup.sh

Why: Verify permission



Step 4

./backup.sh

Why: Run script



Learning

File must have execute permission to run



Day 07 Summary



Today I understood where logs, configs and binaries live in Linux

Practiced troubleshooting like real DevOps scenarios

Feeling more confident with Linux fundamentals

