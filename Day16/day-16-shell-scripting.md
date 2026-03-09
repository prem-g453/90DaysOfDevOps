#### Day 16 – Shell Scripting Basics

&nbsp;

##### Task 1 – First Script



hello.sh



```bash

\#!/bin/bash

echo "Hello, DevOps!"



Output



Hello, DevOps!



Without Shebang:

Script may run with a different shell. Shebang ensures bash interpreter is used.

##### 

##### Task 2 – Variables



variables.sh



\#!/bin/bash

NAME="Prem"

ROLE="DevOps Engineer"

echo "Hello, I am $NAME and I am a $ROLE"



Single vs Double Quotes



Single quotes do not expand variables.

Double quotes expand variables.



##### Task 3 – User Input



greet.sh



\#!/bin/bash

read -p "Enter your name: " name

read -p "Enter your favourite tool: " tool

echo "Hello $name, your favourite tool is $tool"

##### 

##### Task 4 – If Else



check\_number.sh checks whether a number is positive, negative, or zero.



file\_check.sh checks whether a file exists using -f.



##### Task 5 – Service Check Script



server\_check.sh checks service status using systemctl.



What I Learned



Shebang defines the interpreter used to run the script.



Variables store data and can be expanded using $.



Conditional statements allow scripts to make decisions.





