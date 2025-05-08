# Instagram MERN
Full-Stack Instagram Clone using MERN Stack and Socket.IO

How To Import Data Inside Mongo Database:

```
docker cp ./mongo_backup mongo:/data/backup

docker exec -it mongo mongosh

mongorestore /data/backup

mongorestore --db Instagram /data/backup/Instagram

```
