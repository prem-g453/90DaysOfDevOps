#### Day 17 – Shell Scripting: Loops, Arguments \& Error Handling



Today I practiced advanced shell scripting concepts including loops, command-line arguments, package installation through scripts, and basic error handling.





##### Task 1: For Loop



Script: for\_loop.sh



bash

\#!/bin/bash



fruits=("Apple" "Banana" "Mango" "Orange" "Grapes")



for fruit in "${fruits\[@]}"

do

&nbsp; echo "Fruit: $fruit"

done





Output



Fruit: Apple

Fruit: Banana

Fruit: Mango

Fruit: Orange

Fruit: Grapes



Script: count.sh



\#!/bin/bash



for i in {1..10}

do

&nbsp; echo $i

done



Output

1

2

3

4

5

6

7

8

9

10



##### Task 2: While Loop



Script: countdown.sh

\#!/bin/bash



echo "Enter a number:"

read num



while \[ $num -ge 0 ]

do

&nbsp; echo $num

&nbsp; num=$((num-1))

done



echo "Done!"

Output Example

Enter a number:

5

5

4

3

2

1

0

Done!



##### Task 3: Command-Line Arguments



Script: greet.sh

\#!/bin/bash



if \[ -z "$1" ]

then

&nbsp; echo "Usage: ./greet.sh <name>"

else

&nbsp; echo "Hello, $1!"

fi

Output

Hello, Prem!

Script: args\_demo.sh

\#!/bin/bash



echo "Script name: $0"

echo "Total arguments: $#"

echo "All arguments: $@"

Output Example

Script name: ./args\_demo.sh

Total arguments: 3

All arguments: DevOps Linux Docker



##### Task 4: Install Packages via Script



Script: install\_packages.sh

\#!/bin/bash



if \[ "$EUID" -ne 0 ]

then

&nbsp; echo "Please run as root"

&nbsp; exit 1

fi



packages=("nginx" "curl" "wget")



for pkg in "${packages\[@]}"

do

&nbsp; if dpkg -s $pkg \&> /dev/null

&nbsp; then

&nbsp;   echo "$pkg is already installed"

&nbsp; else

&nbsp;   echo "Installing $pkg..."

&nbsp;   apt install -y $pkg

&nbsp; fi

done

Example Output

nginx is already installed

curl is already installed

Installing wget...

Task 5: Error Handling

Script: safe\_script.sh

\#!/bin/bash



set -e



mkdir /tmp/devops-test || echo "Directory already exists"



cd /tmp/devops-test || echo "Failed to enter directory"



touch testfile.txt || echo "File creation failed"



echo "Script completed successfully"

Output

Script completed successfully



##### Key Concepts Learned



1\. How to use \*\*for loops and while loops\*\* in Bash scripting.

2\. How to work with \*\*command-line arguments\*\* using `$1`, `$#`, and `$@`.

3\. How to automate tasks like \*\*package installation using shell scripts\*\*.

4\. How to add \*\*basic error handling using `set -e` and conditional checks\*\*

