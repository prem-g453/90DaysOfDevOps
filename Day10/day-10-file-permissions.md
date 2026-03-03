#### Day 10 Challenge



##### Task 1 – Files Created



Created files using:



touch devops.txt

echo "These are my DevOps notes" > notes.txt

vim script.sh



Inside script.sh:



echo "Hello DevOps"



Checked permissions:



ls -l



##### Task 2 – Reading Files



Read notes.txt:



cat notes.txt



Open script.sh in read-only mode:



vim -R script.sh



Display first 5 lines:



head -n 5 /etc/passwd



Display last 5 lines:



tail -n 5 /etc/passwd



##### Task 3 – Understanding Permissions



Permission format:



rwxrwxrwx

owner group others



Values:



r = 4

w = 2

x = 1



Example:



-rw-r--r--



Owner: read + write

Group: read

Others: read



script.sh was not executable initially because it did not have x permission.



##### Task 4 – Permission Changes



Make script executable:



chmod +x script.sh

./script.sh



After change:



-rwxr-xr-x script.sh



Set devops.txt to read-only:



chmod a-w devops.txt



Now:



-r--r--r-- devops.txt



Set notes.txt to 640:



chmod 640 notes.txt



Result:



-rw-r----- notes.txt



Create directory with 755 permission:



mkdir project

chmod 755 project



Result:



drwxr-xr-x project

##### 

##### Task 5 – Testing Permissions



Trying to write to read-only file:



echo "test" >> devops.txt



Error:



Permission denied



Trying to execute file without execute permission:



./notes.txt



Error:



Permission denied

Commands Used



touch

echo

vim

cat

head

tail

ls -l

chmod

mkdir

