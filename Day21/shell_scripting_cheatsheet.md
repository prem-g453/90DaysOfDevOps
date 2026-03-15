#### Shell Scripting Cheat Sheet

#### 

A quick reference guide for commonly used Bash scripting concepts useful for DevOps workflows.



---

#### 

##### Quick Reference Table

###### 

| Topic | Key Syntax | Example |

|------|------|------|

| Variable | `VAR="value"` | `NAME="DevOps"` |

| Argument | `$1, $2` | `./script.sh arg1` |

| If | `if \[ condition ]; then` | `if \[ -f file ]; then` |

| For loop | `for i in list; do` | `for i in 1 2 3; do` |

| Function | `name() { ... }` | `greet() { echo "Hi"; }` |

| Grep | `grep pattern file` | `grep -i "error" log.txt` |

| Awk | `awk '{print $1}' file` | `awk -F: '{print $1}' /etc/passwd` |

| Sed | `sed 's/old/new/g' file` | `sed -i 's/foo/bar/g' config.txt` |



---

##### 

##### \# 1. Basics

#### 

\## Shebang

Specifies which interpreter should run the script.



```bash

\#!/bin/bash

echo "Hello DevOps"

```



---



\## Running a Script



Make script executable:



```bash

chmod +x script.sh

```



Run script:



```bash

./script.sh

```



or



```bash

bash script.sh

```



---



\## Comments



Single line comment:



```bash

\# This is a comment

```



Inline comment:



```bash

echo "Hello" # prints Hello

```



---



\## Variables



Declare variable:



```bash

NAME="Prem"

```



Use variable:



```bash

echo $NAME

```



Quoted variables:



```bash

"$VAR"   # expands variable

'$VAR'   # literal string

```



---



\## Reading User Input



```bash

read -p "Enter your name: " NAME

echo "Hello $NAME"

```



---



\## Command Line Arguments



```bash

echo "Script name: $0"

echo "First argument: $1"

echo "Total arguments: $#"

echo "All arguments: $@"

echo "Last exit status: $?"

```



---



##### 2\. Operators and Conditionals



\## String Comparisons



```bash

\[ "$a" = "$b" ]

\[ "$a" != "$b" ]

\[ -z "$a" ]   # empty string

\[ -n "$a" ]   # not empty

```



---



\## Integer Comparisons



```bash

\[ $a -eq $b ]

\[ $a -ne $b ]

\[ $a -lt $b ]

\[ $a -gt $b ]

\[ $a -le $b ]

\[ $a -ge $b ]

```



---



\## File Test Operators



```bash

-f file.txt   # file exists

-d folder     # directory exists

-e file       # exists

-r file       # readable

-w file       # writable

-x file       # executable

-s file       # file not empty

```



---



\## If Statement



```bash

if \[ -f "file.txt" ]; then

&nbsp; echo "File exists"

elif \[ -d "folder" ]; then

&nbsp; echo "Directory exists"

else

&nbsp; echo "Not found"

fi

```



---



\## Logical Operators



```bash

\[ condition1 ] \&\& echo "True"



\[ condition1 ] || echo "False"



! \[ condition ]

```



---



\## Case Statement



```bash

case $1 in

start)

&nbsp; echo "Starting service"

&nbsp; ;;

stop)

&nbsp; echo "Stopping service"

&nbsp; ;;

\*)

&nbsp; echo "Usage: start | stop"

&nbsp; ;;

esac

```



---



##### 3\. Loops



\## For Loop (List)



```bash

for i in 1 2 3 4 5

do

&nbsp; echo $i

done

```



---



\## For Loop (C Style)



```bash

for ((i=1;i<=5;i++))

do

&nbsp; echo $i

done

```



---



\## While Loop



```bash

count=1



while \[ $count -le 5 ]

do

&nbsp; echo $count

&nbsp; ((count++))

done

```



---



\## Until Loop



Runs until condition becomes true.



```bash

count=1



until \[ $count -gt 5 ]

do

&nbsp; echo $count

&nbsp; ((count++))

done

```



---



\## Loop Control



Break loop:



```bash

break

```



Skip iteration:



```bash

continue

```



---



\## Loop Over Files



```bash

for file in \*.log

do

&nbsp; echo $file

done

```



---



\## Loop Over Command Output



```bash

cat file.txt | while read line

do

&nbsp; echo $line

done

```



---



##### 4\. Functions



\## Defining Function



```bash

greet() {

&nbsp; echo "Hello DevOps"

}

```



---



\## Calling Function



```bash

greet

```



---



\## Passing Arguments



```bash

add() {

&nbsp; echo $(($1 + $2))

}



add 5 10

```



---



\## Return Values



Return:



```bash

return 1

```



Echo output:



```bash

result=$(add 5 5)

```



---



\## Local Variables



```bash

myfunc() {

&nbsp; local name="Prem"

&nbsp; echo $name

}

```



---



##### 5\. Text Processing Commands



\## grep



```bash

grep "error" log.txt

grep -i "error" log.txt

grep -r "error" .

grep -c "error" log.txt

grep -n "error" log.txt

grep -v "info" log.txt

grep -E "error|fail" log.txt

```



---



\## awk



```bash

awk '{print $1}' file.txt

awk -F: '{print $1}' /etc/passwd

awk 'BEGIN {print "Start"} {print $1} END {print "Done"}' file

```



---



\## sed



```bash

sed 's/foo/bar/' file.txt

sed 's/foo/bar/g' file.txt

sed -i 's/foo/bar/g' file.txt

sed '2d' file.txt

```



---



\## cut



```bash

cut -d',' -f1 file.csv

cut -d':' -f1 /etc/passwd

```



---



\## sort



```bash

sort file.txt

sort -n numbers.txt

sort -r file.txt

sort -u file.txt

```



---



\## uniq



```bash

uniq file.txt

uniq -c file.txt

```



---



\## tr



```bash

tr 'a-z' 'A-Z'

tr -d 'a'

```



---



\## wc



```bash

wc file.txt

wc -l file.txt

wc -w file.txt

wc -c file.txt

```



---



\## head / tail



```bash

head file.txt

head -n 10 file.txt



tail file.txt

tail -n 10 file.txt



tail -f log.txt

```



---



##### 6\. Useful One-Liners



Delete files older than 7 days:



```bash

find /path -type f -mtime +7 -delete

```



Count lines in all log files:



```bash

wc -l \*.log

```



Replace text across files:



```bash

sed -i 's/old/new/g' \*.txt

```



Check if service is running:



```bash

systemctl status nginx

```



Monitor disk usage:



```bash

df -h | grep "/dev"

```



Tail logs for errors:



```bash

tail -f app.log | grep "ERROR"

```



---



##### 7\. Error Handling and Debugging



\## Exit Codes



```bash

echo $?

exit 0

exit 1

```



---



\## set -e



Exit script if a command fails.



```bash

set -e

```



---



\## set -u



Treat unset variables as errors.



```bash

set -u

```



---



\## set -o pipefail



Detect errors in pipelines.



```bash

set -o pipefail

```



---



\## set -x



Debug mode (show commands executed).



```bash

set -x

```



---



\## Trap



```bash

trap 'echo "Cleaning up..."' EXIT

```



---



Shell scripting is a powerful automation tool for DevOps workflows including log analysis, deployments, backups, and monitoring.

