# Install MongoDB on AlmaLinux
- I have installed MongoDB on AlmaLinux 9.0.

## Install MongoDB
1. Create the repository file for MongoDB.
   ```sh
   vim /etc/yum.repos.d/mongodb-org-6.0.repo
   ```
   ```
   [mongodb-org-6.0]
   name=MongoDB Repository
   baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/6.0/x86_64/
   gpgcheck=1
   enabled=1
   gpgkey=https://www.mongodb.org/static/pgp/server-6.0.asc
   ```
1. Install MongoDB.
   ```sh
   dnf install mongodb-org
   ```

## Create a Database and Collection
1. Start MongoDB.
   ```sh
   systemctl start mongod
   ```
1. Connect to MongoDB.
   ```sh
   mongosh
   ```
1. Create a new database.
   ```
   use testdb
   ```
1. Create a new collection.
   ```
    db.createCollection("sample")
   ```

## Insert a Data into a Collection
1. Switch
   ```
   use testdb
   ```
1. Insert.
   ```
   db.sample.insert({name:"john"});
   ```
1. Check.
   ```
   do.sample.find().pretty()
   ```
