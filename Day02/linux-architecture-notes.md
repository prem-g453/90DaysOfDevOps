#### Linux Architecture – Day 02 Notes

##### Core Components of Linux



->Kernel



Core of the Linux OS



Directly interacts with hardware (CPU, Memory, Disk, Network)



Responsible for:



Process management



Memory management



Device drivers



File systems



System calls



Without kernel, Linux cannot function.



->User Space



Where users and applications run



Examples:



Bash



Nginx



Docker



Python apps



Communicates with kernel using system calls



DevOps mostly works in user space.



->Init System (systemd)



First process started by kernel



Has PID 1



Responsible for:



Starting services



Managing services



Handling service failures



Boot process management



Modern Linux uses systemd as init system.



##### How Processes Are Created \& Managed Process Creation



Every process has a PID



Created using:



fork() → creates child process



exec() → loads program into memory



Example:



When you run nginx, a process is created with a PID.



Process States

State	Meaning

Running (R)	Actively using CPU

Sleeping (S)	Waiting for resource (most common)

Stopped (T)	Paused manually

Zombie (Z)	Finished but not cleaned by parent

Dead	Terminated and removed



Zombie processes happen if parent doesn't collect child exit status.



##### How Linux Manages Processes



Each process has:



PID



PPID (Parent PID)



CPU usage



Memory usage



Managed by kernel scheduler



Can be:



Killed



Restarted



Prioritized (nice value)



##### What systemd Does \& Why It Matters systemd Responsibilities:



Starts services at boot



Restarts crashed services



Manages background services (daemons)



Handles logging (journald)



Controls service dependencies



Why It Matters for DevOps:



If app crashes → systemd can auto-restart



During incident → check logs via journalctl



Manage production services reliably



##### 5 Daily Linux Commands (DevOps Use)



ps aux            # View running processes

top               # Real-time CPU \& memory usage

htop              # Better version of top

systemctl status nginx

journalctl -xe

🔥 Why This Matters



Helps debug crashed services



Helps fix high CPU/memory issues



Helps understand service failures



Foundation for production troubleshooting



Linux runs almost every production server.



Understanding this saves hours during incidents.



