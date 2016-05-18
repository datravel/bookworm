# Admin Cheatsheet

## Kafka
1. Check log size
```
g1:~# df -h /srv/storage/sas/raid/data/kafka/log
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdb1       549G  483G   39G  93% /srv/storage/sas/raid
```

## Mongo
1. Check mongo instances state
```
g1% echo 'rs.status()' |  sudo docker exec -i mongo3 mongo | egrep 'name|stateStr'
```

## Teamcity
1. Delete agent temporary files
```
g1:~# rm -rf /srv/storage/ssd/raid/data/teamcity-agent/var/.old/*
```
