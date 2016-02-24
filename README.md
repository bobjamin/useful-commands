# Useful Commands

_Using Ubuntu 14.04.3 LTS_

* View recently installed packages

```awk '$3~/^install$/ {print $4;}' /var/log/dpkg.log```

* List all users

```cut -d: -f1 /etc/passwd```

* Print the amount of items in the current directory every 2 seconds

```while sleep 2; do ls | wc -l; done```

* Capture a local backup of a collection on a remote mongo database and store in a zip file

```mongodump --host server.url --db db_name --collection coll_name --out - | zip collection_dump.zip```

* Delete a remote git branch

```git push origin --delete BRANCH```

* Set git credentials

```git config --global user.name "User"```

```git config --global user.email "foo@bar.com"```

* Display git settings

```git config --list```

* Display a menu showing alternative JRE installations

```sudo update-alternatives --config java```

* Insert a new line above every line that matches your phrase and save the output

```sed '/phrase/{x;p;x;}' input.txt > output.txt```

* Echo out the line count and length of longest line in a file

```echo "Line count:" `wc -l < FILENAME` && echo "Longest line length: " `wc -L < FILENAME````

* Display a snapshot of the process using the most memory

```ps aux --sort -rss | head -n 2```

* Display a snapshot of the process with heaviest CPU usage

```ps aux | sort -rk 3,3 | head -n 2```

* Grep for something and display the 3 lines before and after your match

```grep -A 3 -B 3 "something" example.log```

* Ping scan the specified subnet and return a list of IP's that respond

```nmap 192.168.0.0/24```

* Identify all of the hostnames of the IP's found in a specified subnet

```nmap -sL 192.168.0.0/24```

* Check if a port is in use

```lsof -i :27017```

* Remove all but the 5 latest files in a directory

```rm `ls -t | awk 'NR>5'````

* Check CRON installation log

```grep CRON /var/log/syslog```

* Generate key pair

```ssh-keygen -t rsa```

* Force SSH to use a private key

```ssh -i /path/to/private host@host.com```

* SSH maximum verbosity

```ssh -vvv host@host.com```

* Add user

```sudo useradd caleb```

* Run apache configuration syntax test

```apachectl configtest```

* Grab a file from a ftp server with curl

```$ curl -u ftpuser:ftppass -O ftp://ftp_server/test.txt```

* Find all hidden files in a directory

```find /tmp -type f -name ".*"```

* Substitute "foo" with "bar" ONLY for lines which contain "baz"

```sed '/baz/s/foo/bar/g'```

* Find the numbers in my log file between "100% complete - " and "files moved" and add them up

```cat example.log | grep -o -P '(?<=100% complete - ).*(?=files moved)' |  awk '{ SUM += $1} END { print SUM }'```

* Set an environment variable for one command only

```var=value command'```

* Find the unique occurences of new lines containing the text "key:" in all of the files in the current directory

```grep -rh "^key:" | sort -u```
