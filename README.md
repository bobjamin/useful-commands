# Useful Commands

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
