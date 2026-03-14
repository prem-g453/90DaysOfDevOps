#### Day 20 – Bash Log Analyzer



Objective:



Create a Bash script that analyzes system logs and generates a summary report.





Script



log\_analyzer.sh



##### The script performs:



\- Accepts a log file as input

\- Validates file existence

\- Counts errors

\- Finds critical events

\- Identifies top error messages

\- Generates a report

\- Archives processed logs







##### Tools Used



\- grep → search patterns in logs

\- awk → text processing

\- sort → sort results

\- uniq → count unique entries

\- wc → count lines

\- mv → move processed logs



##### Sample Output



Total Errors: 6



--- Critical Events ---

Line 4: CRITICAL Disk space below threshold

Line 9: CRITICAL Database connection lost



--- Top 5 Error Messages ---

3 Connection timed out

1 File not found

1 Permission denied



##### Generated Report



File: log\_report\_<date>.txt



Includes:



\- Date

\- Log file name

\- Total lines

\- Error count

\- Top errors

\- Critical events



##### Key Learnings



1\. Automating log analysis using Bash scripting.

2\. Using grep, awk, sort, and uniq together for text processing.

3\. Creating automated reports and archiving logs.

