# Admin Cheatsheet

## Mongo
1. Check mongo instances state
```
g1% echo 'rs.status()' |  sudo docker exec -i mongo3 mongo | egrep 'name|stateStr'
```
