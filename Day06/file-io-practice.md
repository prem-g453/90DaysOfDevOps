#### Day 06 – Linux Fundamentals File Read Write Practice



Today I practiced basic file operations in Linux using simple commands



##### created file



touch notes.txt

This created an empty file



Then I wrote text inside the file



echo "Line 1 - Learning Linux basics" > notes.txt

This wrote the first line and created content



echo "Line 2 - Practicing file operations" >> notes.txt

This appended a new line without deleting previous content



echo "Line 3 - DevOps requires strong fundamentals" >> notes.txt



##### tee command



echo "Line 4 - Added using tee command" | tee -a notes.txt

This displayed output on terminal and also appended into file



##### read file



cat notes.txt

This showed full file content



head -n 2 notes.txt

This showed first two lines



tail -n 2 notes.txt

This showed last two lines



Today I clearly understood the difference between > and >>

I also learned how tee helps in logging and scripting



Reading and writing files is very important for handling logs and configs in DevOps





