#### Day 09 Challenge – Linux User \& Group Management



Objective



Practice creating users, groups, assigning permissions and managing shared directories.

##### 

##### Task 1 – Users Created



Created users with home directories and passwords:



tokyo



berlin



professor



nairobi



Verified using:



cat /etc/passwd

ls /home



All users successfully created with home directories.



##### Task 2 – Groups Created

##### 

Created groups:



developers



admins



project-team



Verified using:



cat /etc/group



##### Task 3 – Group Assignments



Assigned users to groups:



tokyo → developers



berlin → developers, admins



professor → admins



nairobi → project-team



tokyo → project-team



Verified using:



groups tokyo

groups berlin

groups professor

groups nairobi



Confirmed correct group membership.



##### Task 4 – Shared Directory Setup



Created shared directory:



/opt/dev-project



Steps performed:



Set group owner to developers



Set permissions to 775



Commands used:



sudo mkdir /opt/dev-project

sudo chgrp developers /opt/dev-project

sudo chmod 775 /opt/dev-project

ls -ld /opt/dev-project



Tested file creation:



sudo -u tokyo touch /opt/dev-project/test1.txt

sudo -u berlin touch /opt/dev-project/test2.txt



Both users successfully created files.



##### Task 5 – Team Workspace Setup



Created workspace directory:



/opt/team-workspace



Steps performed:



Created user nairobi



Created group project-team



Added nairobi and tokyo to project-team



Set group ownership



Set permissions to 775



Commands used:



sudo mkdir /opt/team-workspace

sudo chgrp project-team /opt/team-workspace

sudo chmod 775 /opt/team-workspace

ls -ld /opt/team-workspace



Tested:



sudo -u nairobi touch /opt/team-workspace/work.txt



File creation successful.



##### Commands Used



\-useradd -m

\-passwd

\-groupadd

\-usermod -aG

\-groups

\-mkdir

\-chgrp

\-chmod

\-ls -ld

\-sudo -u



##### What I Learned



Group permissions control real collaboration in Linux systems



The -aG flag is important while adding users to multiple groups



775 permission allows owner and group full access while others get read and execute

