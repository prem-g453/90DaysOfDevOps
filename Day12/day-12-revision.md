#### Day 12 – Breather \& Revision (Days 01–11)



Take a pause to revise and consolidate the concepts learned in Days 01–11.

This helps reinforce Linux fundamentals before moving forward.



Mindset \& Plan Review (Day 01)



My goal is to become comfortable with Linux fundamentals for DevOps.



Focus areas: Linux commands, permissions, services, and troubleshooting.



The learning plan still aligns with my goal of becoming a DevOps Engineer.



Improvement needed: practice more real terminal scenarios instead of only reading notes.





##### Processes \& Services Review (Day 04 \& Day 05)





Commands Practiced

ps aux

systemctl status nginx

journalctl -u nginx

Observations



ps aux shows all running processes with their PID and resource usage.



systemctl status nginx shows if the nginx service is running or stopped.



journalctl -u nginx displays logs related to the nginx service.



These commands help quickly diagnose service failures or server issues.



File Skills Practice (Days 06–11)

Commands Practiced



Create file and add content



echo "DevOps practice file" >> devops.txt



Check file permissions



ls -l devops.txt



Change file permissions



chmod 644 devops.txt



Create directory



mkdir practice-folder



Copy file



cp devops.txt practice-folder/

Cheat Sheet Refresh (Day 03)

5 Commands I Would Use First in an Incident

ls -l



Check files and permissions.



ps aux



Check running processes.



systemctl status <service>



Verify if a service is running.



journalctl -xe



Check system logs for errors.



df -h



Check disk space usage.



User \& Group Management Review (Day 09 / Day 11)

Scenario Practice



Create a new user



sudo useradd devuser



Set password



sudo passwd devuser



Check user information



id devuser



Change file ownership



sudo chown devuser devops.txt



Verify ownership



ls -l devops.txt

Mini Self-Check

##### 

##### 1\. Which 3 commands save you the most time right now and why?



ps aux

Shows all running processes and helps identify issues quickly.



systemctl status

Quickly checks whether a service is running or failed.



ls -l

Helps inspect file permissions and ownership instantly.



##### 2\. How do you check if a service is healthy?



Commands I run first:



systemctl status nginx

ps aux | grep nginx

journalctl -u nginx



These commands help verify if the service is running and check logs if something fails.



##### 3\. How do you safely change ownership and permissions?



Example:



Change file ownership



sudo chown prem devops.txt



Change file permissions



chmod 644 devops.txt



I always verify using:



ls -l



before and after making changes.



##### 4\. What will you focus on improving in the next 3 days?



Practicing Linux troubleshooting scenarios



Understanding file permissions deeply (chmod numeric values)



Learning more service management commands



Getting comfortable working fully from the terminal



Key Takeaways



Linux fundamentals like permissions, processes, and services are essential for DevOps.



Commands like systemctl, ps, chmod, and chown are used frequently.



Practicing commands regularly helps build muscle memory.

