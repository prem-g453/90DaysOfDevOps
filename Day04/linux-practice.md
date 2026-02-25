#### Day 04 – Linux Practice: Processes and Services



##### Process Checks



Checking Running Processes



Command:

ps aux | head



Observation:

Displayed active processes with PID, CPU usage, memory usage, and command details.

Observed system processes running under root and user-level processes under my account.



Real-Time Process Monitoring



Command:

top



Observation:

Saw overall CPU and memory usage at the top.

Observed running, sleeping, and zombie tasks.

Noticed systemd, bash, and dockerd processes consuming minimal resources.



Finding a Specific Process



Command:

pgrep docker



Observation:

Returned a PID number, confirming that the Docker daemon is running.



##### Service Checks



Service Inspected: docker.service



Checking Service Status



Command:

systemctl status docker



Observation:

Service state: active (running)

Service is enabled at boot.

Main PID displayed.

No recent failure messages.



Listing Running Services



Command:

systemctl list-units --type=service --state=running



Observation:

Displayed currently running services including:

docker.service

cron.service

ssh.service

systemd-journald.service



Log Checks

##### 

##### Viewing Service Logs



Command:

journalctl -u docker --no-pager | tail -n 20



Observation:

Docker daemon started successfully.

Network bridge initialized.

No recent error entries found.



##### Viewing System Logs



Command:

tail -n 50 /var/log/syslog



Observation:

Observed service startup messages.

Regular cron activity logs.

No critical system warnings.



##### Mini Troubleshooting Flow



Scenario: Docker container not starting



Step 1:

systemctl status docker

Verify Docker service is running.



Step 2:

docker ps -a

Check container status and exit codes.



Step 3:

journalctl -u docker

Inspect service logs for errors.



Step 4:

sudo systemctl restart docker

Restart the service if required.



Step 5:

docker logs <container\_id>

Inspect container-specific logs.



Key Learnings



Practiced checking running processes.

Understood how to inspect systemd services.

Learned how to use journalctl for service logs.

Built a simple troubleshooting flow for production scenarios.

Improved command confidence through hands-on practice.

