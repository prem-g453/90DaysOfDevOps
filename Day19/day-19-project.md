#### Day 19 – Shell Scripting Project: Log Rotation, Backup \& Crontab

#### 

##### Overview



In this project, I applied shell scripting concepts to automate common server maintenance tasks such as log rotation, backups, and scheduling jobs using cron.




    
##### Task 1 – Log Rotation Script



Script: `log\_rotate.sh`



```bash

\#!/bin/bash

set -euo pipefail



LOG\_DIR=$1



if \[ ! -d "$LOG\_DIR" ]; then

&nbsp;   echo "Error: Directory does not exist"

&nbsp;   exit 1

fi



compressed=0

deleted=0



for file in $(find "$LOG\_DIR" -name "\*.log" -mtime +7 2>/dev/null); do

&nbsp;   gzip "$file"

&nbsp;   ((compressed++))

done



for file in $(find "$LOG\_DIR" -name "\*.gz" -mtime +30 2>/dev/null); do

&nbsp;   rm "$file"

&nbsp;   ((deleted++))

done



echo "Compressed files: $compressed"

echo "Deleted files: $deleted"

```



Example Command



```bash

./log\_rotate.sh testlogs

```



\## Sample Output



```

Compressed files: 2

Deleted files: 0

```



---



##### Task 2 – Server Backup Script



Script: `backup.sh`



```bash

\#!/bin/bash

set -euo pipefail



SRC=$1

DEST=$2



if \[ ! -d "$SRC" ]; then

&nbsp;   echo "Source directory does not exist"

&nbsp;   exit 1

fi



mkdir -p "$DEST"



DATE=$(date +%Y-%m-%d)

ARCHIVE="$DEST/backup-$DATE.tar.gz"



tar -czf "$ARCHIVE" "$SRC"



if \[ -f "$ARCHIVE" ]; then

&nbsp;   echo "Backup created: $ARCHIVE"

&nbsp;   du -h "$ARCHIVE"

else

&nbsp;   echo "Backup failed"

&nbsp;   exit 1

fi



find "$DEST" -name "backup-\*.tar.gz" -mtime +14 -delete

```



Example Command



```bash

./backup.sh /etc ./backups

```



Sample Output



```

Backup created: backups/backup-2026-03-13.tar.gz

Size: 15M

```



---



##### Task 3 – Cron Jobs



Check existing cron jobs



```bash

crontab -l

```





Cron Entries



Run log rotation every day at \*\*2 AM\*\*



```

0 2 \* \* \* /home/user/log\_rotate.sh /var/log/myapp

```



Run backup every \*\*Sunday at 3 AM\*\*



```

0 3 \* \* 0 /home/user/backup.sh /var/www /backup

```



Run health check every \*\*5 minutes\*\*



```

\*/5 \* \* \* \* /home/user/health\_check.sh

```



---



##### Task 4 – Maintenance Script



Script: `maintenance.sh`



```bash

\#!/bin/bash



LOGFILE="/var/log/maintenance.log"



echo "$(date) : Starting maintenance" >> $LOGFILE



./log\_rotate.sh /var/log >> $LOGFILE 2>\&1

./backup.sh /etc ./backups >> $LOGFILE 2>\&1



echo "$(date) : Maintenance finished" >> $LOGFILE

```



Run Script



```bash

./maintenance.sh

```



Cron Entry



Run maintenance every day at \*\*1 AM\*\*



```

0 1 \* \* \* /home/user/maintenance.sh

```



---



##### What I Learned



\* Automating repetitive system tasks using shell scripts

\* Managing log files and backups on Linux servers

\* Scheduling automated jobs using cron



