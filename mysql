=======================================================================================
                Database Script

[root@ip-172-31-64-248 ~]# cat    backup.sh
#!/bin/bash

# MySQL credentials

USER="root"
#PASSWORD="your_mysql_password"
HOST="localhost"
DB_NAME="rohit"

# Backup destination directory

BACKUP_DIR="/tmp/backup"
DATE=$(date +"%Y-%m-%d"-%H:%M)  # Create a timestamp for the backup file
BACKUP_FILE="$BACKUP_DIR/$DB_NAME-$DATE.sql"

# Create backup directory if it doesn't exist
mkdir -p "$BACKUP_DIR"

# Run mysqldump to create the backup
mysqldump -u $USER -h $HOST $DB_NAME > $BACKUP_FILE

# Check if the backup was successful
if [ $? -eq 0 ]; then
  echo "Backup successful! Backup file is saved as $BACKUP_FILE"
else
  echo "Backup failed!"
fi

[root@ip-172-31-64-248 ~]#

==================================================================================================================
              Database

[root@ip-172-31-64-248 ~]#
[root@ip-172-31-64-248 ~]# mysql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.5.25-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> use rohit
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
MariaDB [rohit]>
MariaDB [rohit]> show tables;
+-----------------+
| Tables_in_rohit |
+-----------------+
| users           |
+-----------------+
1 row in set (0.000 sec)

MariaDB [rohit]>
MariaDB [rohit]> exit
Bye
=======================================================================================================================
        After running the command output

[root@ip-172-31-64-248 ~]# sh   backup.sh
Backup successful! Backup file is saved as /tmp/backup/rohit-2024-12-31-06:33.sql
[root@ip-172-31-64-248 ~]#
[root@ip-172-31-64-248 ~]# ls  -l   /tmp/backup
total 4
-rw-r--r--. 1 root root 2859 Dec 31 06:33 rohit-2024-12-31-06:33.sql
[root@ip-172-31-64-248 ~]#
