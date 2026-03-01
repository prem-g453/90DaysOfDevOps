#### DAY 08 – CLOUD SERVER SETUP (DOCKER + NGINX + DEPLOYMENT)

#### 

Objective

Deploy a real web server on cloud, access it from internet and extract logs.



Cloud Provider Used

AWS EC2 (Ubuntu)

##### 

##### PART 1 – Launch Cloud Instance \& SSH



Created EC2 instance (Ubuntu 22.04)



Downloaded key pair (.pem file)



Allowed inbound rules:



Port 22 (SSH)



Port 80 (HTTP)



Connect to server:



ssh -i my-key.pem ubuntu@<public-ip>



Verified connection:

whoami

uname -a



This confirms remote access to cloud server.



##### PART 2 – Install Docker and Nginx



Update system:



sudo apt update

sudo apt upgrade -y



Install Docker:



sudo apt install docker.io -y

sudo systemctl start docker

sudo systemctl enable docker



Check Docker:



docker --version



Install Nginx:



sudo apt install nginx -y

sudo systemctl start nginx

sudo systemctl enable nginx



Check status:



sudo systemctl status nginx



Nginx should show active (running)



##### PART 3 – Security Group Configuration



If website not loading:



Check EC2 Security Group

Add inbound rule:



Type: HTTP

Port: 80

Source: 0.0.0.0/0



Test in browser:



http://<public-ip>



Nginx welcome page appears.



This confirms web server is publicly accessible.



##### PART 4 – Nginx Logs



Access logs location:



/var/log/nginx/access.log

/var/log/nginx/error.log



View logs:



sudo cat /var/log/nginx/access.log



Save logs to file:



sudo cp /var/log/nginx/access.log ~/nginx-logs.txt



Download to local machine:



scp -i my-key.pem ubuntu@<public-ip>:~/nginx-logs.txt .



KEY COMMANDS USED



ssh

apt

systemctl

docker

cat

scp



CHALLENGES FACED



Port 80 not enabled initially



Website not loading



Fixed by updating security group



WHAT I LEARNED



How to launch a cloud server



How to connect using SSH



How to install and manage services



How security groups control traffic



How to access and extract logs



WHY THIS IS IMPORTANT FOR DEVOPS



This is real production work:



Infrastructure provisioning



Remote server management



Service deployment



Log monitoring



Security configuration



Day 08 complete.

