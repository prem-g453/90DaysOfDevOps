#### Day 18 – Shell Scripting: Functions \& Intermediate Concepts



##### Overview



Today I learned how to write clean and reusable shell scripts using functions.

I also explored strict mode (set -euo pipefail), return values, and local variables to make scripts safer and more reliable.



##### Key topics covered:



Writing and calling functions



Passing arguments to functions



Using set -euo pipefail



Working with local variables



Building a reusable system info reporting script



##### Task 1 – Basic Functions



Script: functions.sh

\#!/bin/bash



greet() {

&nbsp; echo "Hello, $1!"

}



add() {

&nbsp; sum=$(( $1 + $2 ))

&nbsp; echo "Sum: $sum"

}



greet "Prem"

add 5 7

Output

Hello, Prem!

Sum: 12



##### Task 2 – Functions with Return Values



Script: disk\_check.sh

\#!/bin/bash



check\_disk() {

&nbsp; echo "Disk Usage:"

&nbsp; df -h /

}



check\_memory() {

&nbsp; echo "Memory Usage:"

&nbsp; free -h

}



echo "System Resource Check"

echo "---------------------"



check\_disk

echo

check\_memory

Output

System Resource Check

---------------------



Disk Usage:

Filesystem      Size  Used Avail Use% Mounted on

/dev/sda1        50G   20G   28G  42% /



Memory Usage:

&nbsp;             total        used        free

Mem:           7.6G        2.1G        3.8G

##### 

##### Task 3 – Strict Mode (set -euo pipefail)



Script: strict\_demo.sh

\#!/bin/bash

set -euo pipefail



echo "Testing strict mode"



\# Undefined variable

echo $UNDEFINED\_VAR



\# Command failure

false



\# Pipe failure

grep "test" nonexistentfile | sort

Explanation of Strict Mode

set -e



Stops the script immediately if any command exits with a non-zero status (error).



Example:



false



The script exits immediately.



set -u



Treats undefined variables as errors.



Example:



echo $UNDEFINED\_VAR



Result:



bash: UNDEFINED\_VAR: unbound variable

set -o pipefail



If any command in a pipeline fails, the entire pipeline fails.



Example:



grep "test" file.txt | sort



If grep fails, the pipeline returns failure instead of continuing.



##### Task 4 – Local Variables



Script: local\_demo.sh

\#!/bin/bash



demo\_local() {

&nbsp; local message="This is a local variable"

&nbsp; echo $message

}



demo\_global() {

&nbsp; message="This is a global variable"

}



demo\_local

echo "Outside function: $message"



demo\_global

echo "Outside after global function: $message"

Output

This is a local variable

Outside function:

Outside after global function: This is a global variable

Explanation



local variables only exist inside the function



Normal variables become global



##### Task 5 – System Info Reporter



Script: system\_info.sh

\#!/bin/bash

set -euo pipefail



print\_system\_info() {

&nbsp; echo "===== System Information ====="

&nbsp; hostname

&nbsp; uname -a

}



print\_uptime() {

&nbsp; echo

&nbsp; echo "===== System Uptime ====="

&nbsp; uptime

}



print\_disk\_usage() {

&nbsp; echo

&nbsp; echo "===== Disk Usage (Top 5) ====="

&nbsp; du -ah / | sort -rh | head -5

}



print\_memory\_usage() {

&nbsp; echo

&nbsp; echo "===== Memory Usage ====="

&nbsp; free -h

}



print\_cpu\_process() {

&nbsp; echo

&nbsp; echo "===== Top 5 CPU Processes ====="

&nbsp; ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head -6

}



main() {

&nbsp; print\_system\_info

&nbsp; print\_uptime

&nbsp; print\_disk\_usage

&nbsp; print\_memory\_usage

&nbsp; print\_cpu\_process

}



main

Example Output

===== System Information =====

hostname: ubuntu

Linux ubuntu 5.15.0



===== System Uptime =====

10:32:11 up 3 days, 4:10



===== Disk Usage (Top 5) =====

2.1G /var

1.8G /usr

1.2G /home



===== Memory Usage =====

&nbsp;             total        used        free

Mem:           7.6G        2.3G        3.5G



===== Top 5 CPU Processes =====

PID   CMD                        %CPU

1234  firefox                     15.2

2345  chrome                      10.1

##### 

##### What I Learned



->Functions make scripts reusable



Functions allow us to write code once and reuse it multiple times in the script.



->Strict mode improves script reliability



Using set -euo pipefail helps catch errors early and prevents silent failures.



->Local variables prevent conflicts



Using local inside functions keeps variables contained and avoids unexpected behavior.

