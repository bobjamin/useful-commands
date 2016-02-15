# Useful Commands

_Using Ubuntu 14.04.3 LTS_


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
