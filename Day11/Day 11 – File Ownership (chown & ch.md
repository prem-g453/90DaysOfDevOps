#### Day 11 – File Ownership (chown \& chgrp)

Task



Learn how file ownership works in Linux and how to modify owner and group using chown and chgrp.



##### Task 1: Understanding Ownership



Command Used

ls -l

Example Output

-rw-r--r-- 1 prem prem 0 Mar 4 devops-file.txt

Format Explanation

-rw-r--r-- 1 owner group size date filename

Column	Meaning

owner	User who owns the file

group	Group that has access to the file

Difference Between Owner and Group



Owner



The user who created or owns the file



Has control over permissions and file operations



Group



A collection of users



Members of the group can access the file based on group permissions



##### Task 2: Basic chown Operations



Create File

touch devops-file.txt

Check Owner

ls -l devops-file.txt

Create Users

sudo useradd tokyo

sudo useradd berlin

Change Owner

sudo chown tokyo devops-file.txt

Verify

ls -l devops-file.txt

Change Owner Again

sudo chown berlin devops-file.txt

Verify

ls -l devops-file.txt



##### Task 3: Basic chgrp Operations



Create File

touch team-notes.txt

Create Group

sudo groupadd heist-team

Change Group

sudo chgrp heist-team team-notes.txt

Verify

ls -l team-notes.txt



##### Task 4: Combined Owner \& Group Change



Create File

touch project-config.yaml

Create User

sudo useradd professor

Change Owner and Group Together

sudo chown professor:heist-team project-config.yaml

Create Directory

mkdir app-logs

Change Ownership

sudo chown berlin:heist-team app-logs

Verify

ls -l

##### 

##### Task 5: Recursive Ownership



Create Directory Structure

mkdir -p heist-project/vault

mkdir -p heist-project/plans

Create Files

touch heist-project/vault/gold.txt

touch heist-project/plans/strategy.conf

Create Group

sudo groupadd planners

Change Ownership Recursively

sudo chown -R professor:planners heist-project/

Verify

ls -lR heist-project/

##### 

##### Task 6: Practice Challenge



Create Users

sudo useradd tokyo

sudo useradd berlin

sudo useradd nairobi

Create Groups

sudo groupadd vault-team

sudo groupadd tech-team

Create Directory

mkdir bank-heist

Create Files

touch bank-heist/access-codes.txt

touch bank-heist/blueprints.pdf

touch bank-heist/escape-plan.txt

Set Ownership

sudo chown tokyo:vault-team bank-heist/access-codes.txt

sudo chown berlin:tech-team bank-heist/blueprints.pdf

sudo chown nairobi:vault-team bank-heist/escape-plan.txt

Verify

ls -l bank-heist/

Files \& Directories Created



devops-file.txt



team-notes.txt



project-config.yaml



app-logs/



heist-project/



bank-heist/



##### Ownership Changes



File	Before	After

devops-file.txt	prem:prem	tokyo → berlin

team-notes.txt	prem:prem	prem:heist-team

project-config.yaml	prem:prem	professor:heist-team

app-logs	prem:prem	berlin:heist-team

heist-project	prem:prem	professor:planners

access-codes.txt	prem:prem	tokyo:vault-team

blueprints.pdf	prem:prem	berlin:tech-team

escape-plan.txt	prem:prem	nairobi:vault-team



##### Commands Used



ls -l

touch filename

mkdir directory

sudo useradd username

sudo groupadd groupname

sudo chown owner filename

sudo chgrp groupname filename

sudo chown owner:group filename

sudo chown -R owner:group directory

ls -lR

What I Learned



Every file in Linux has an owner and a group.



The chown command changes the owner, while chgrp changes the group.



The -R flag allows recursive ownership changes for directories and all files inside them.

