# Task 2

Your task is:
1. Create a stateful set for the official `mongo` image
  * Set env variables `MONGO_INITDB_ROOT_USERNAME=root` and `MONGO_INITDB_ROOT_PASSWORD=root`
2. Create a service to point to the mongo stateful set (port 27017 same as targetPort)
3. Move the provided dump file into the running mongo container (`kubectl cp`)
4. Restore the dump as a backup with the command:
  * ```mongorestore -u $MONGO_INITDB_ROOT_USERNAME -p $MONGO_INITDB_ROOT_USERNAME --gzip --authenticationDatabase=admin --archive={location}/dump.gz```
5. Update the App hosted in the Task 1 with an env variable `MONGODB_URL` (dump expects database named as `secret`, can set auth db on url with `?authSource=admin`)
  * With recommended env names url should be ```mongodb://root:root@mongo/secret?authSource=admin```
6. Make the App's `/secret` link work
