#### Day 03 – Linux Commands Practice



Today I practiced important Linux commands that I will use frequently as a DevOps engineer.

I focused on understanding the commands instead of just memorizing them.

&nbsp;

##### Process Management



ps aux – Shows all running processes

ps -ef – Detailed process list

top – Real-time CPU \& memory usage

htop – Better interactive version of top

kill <PID> – Stop a process

kill -9 <PID> – Force stop a process

pkill <name> – Kill process by name

jobs – Show background jobs

bg – Run job in background

fg – Bring job to foreground



##### File System Commands



pwd – Shows current directory

ls -la – List all files with details

cd <dir> – Change directory

mkdir <dir> – Create new folder

rm -rf <dir> – Delete folder forcefully

cp -r src dest – Copy files or folders

mv src dest – Move or rename file

touch file.txt – Create new file

cat file.txt – View file content

less file.txt – View file page by page

head -n 20 file.txt – View first 20 lines

tail -f file.log – Monitor logs live

du -sh \* – Check folder sizes

df -h – Check disk space



##### Networking Troubleshooting



ping google.com – Check internet connectivity

ip addr – View IP address

ss -tulnp – Check listening ports

netstat -tulnp – Network statistics

curl example.com – Test API or website

wget <url> – Download files

dig google.com – Check DNS resolution

traceroute google.com – Trace network path



##### System \& Logs



uname -a – Show system information

whoami – Current logged-in user

uptime – System running time

free -h – Check memory usage

history – View command history

grep "error" file.log – Search for errors in logs

find / -name file.txt – Find file in system

chmod 755 file – Change file permissions

chown user:file file – Change ownership



##### My Most Useful Commands



tail -f – Best command for real-time log monitoring

ss -tulnp – Very helpful for port troubleshooting

df -h – First command to check when system is slow

ps aux | grep <name> – Quick way to check running process



##### What I Learned Today



Production problems are solved using simple Linux commands.

The better I get at using them, the faster I can troubleshoot real issues.



