# Admin Cheatsheet

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
