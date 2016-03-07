# Useful Commands

_Using Ubuntu 14.04.3 LTS_

* Show numeric version of file permission 

```stat -c "%a %n" /path/to/file```

* Bump process priority (-20 to 20 _negatives require root_) -20 highest, 20 lowest

```nice -10 command```

* View a list of all locally installed packages 

```dpkg --get-selections | grep -v deinstall```

* View recently installed packages

```awk '$3~/^install$/ {print $4;}' /var/log/dpkg.log```

* List all users

```cut -d: -f1 /etc/passwd```

* Print the amount of items in the current directory every 2 seconds

```while sleep 2; do ls | wc -l; done```

* Capture a local backup of a collection on a remote mongo database and store in a zip file

```mongodump --host server.url --db db_name --collection coll_name --out - | zip collection_dump.zip```

* Checkout git branch and update working directory 

```git checkout branch_name```

* Show all local and remote git branches

```git branch -av```

* Delete a remote git branch

```git push origin --delete BRANCH```

* Set git credentials

```git config --global user.name "User"```

```git config --global user.email "foo@bar.com"```

* Display git settings

```git config --list```

* Display a menu showing alternative JRE installations

```sudo update-alternatives --config java```

* Restart apache

```/etc/init.d/apache2 restart```

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

* SFTP using a private key for authentication

```sftp -o IdentityFile=/path/to/private_key user@host```

* Show available aliases

```alias``` or ```compgen -a```

* Remove all aliases

```unalias -a```

* Remove a specific alias

```unalias alias_name```

* Find all empty files in the home directory

```find ~ -empty```

* Open a file in vim on a specific line

```vim +14 Application.java```

* Open vim on the first match of the specified term

```vim +/main Application.java```

* Ignore whitespace when comparing files

```diff -w a.c b.c```

* Show android devices connected

```adb devices```

* Enter device shell using android debug bridge

```adb shell```

* Take a screencap of your device and save it to a png on your machine

```adb shell screencap -p | perl -pe 's/\x0D\x0A/\x0A/g' > screen.png```

* Convert a pdf document to a text file

```pdftotext source.pdf```

* Get the latest Docker package

```curl -fsSL https://get.docker.com/ | sh```

* Add user to Docker group

```sudo usermod -aG docker username```

* Start the Docker daemon

```sudo service docker start```

* Create and run a Docker container using a specific image

```docker run image_name```

* View local Docker images

```docker images```

* Build a Docker image using the Dockerfile in the current directory

```docker build -t image_name .```

* Tag a Docker (image id, accountname/imagename:version-label/tag)

```docker tag 123abc123abc cbrowne/mydocker:latest```

* Login to Docker Hub

```docker login --username=cbrowne --email=calebrjbrowne@gmail.com```

* Push an image to a Docker Hub repository

```docker push cbrowne/mydocker```

* Remove Docker local image by ID or name

```docker rmi -f 7d9495d03763```

```docker rmi -f cbrowne/mydocker```

* Run an interactive shell in a Docker image

```docker run -i -t mydocker /bin/bash```

* Run an interactive shell in a Docker image and set the hostname

```sudo docker run -h mydocker -i -t mydocker /bin/bash```

* Cat backwards

```tac my.log```
