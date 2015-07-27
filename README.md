# A Docker image of PostgreSQL 9.3
#### Issues:
You need to change the default storage driver before starting Docker daemon by updating DOCKER_OPTS

      DOCKER_OPTS="--storage-driver=devicemapper"

Update[7/27/2015]: Another work-around for this issue is using --no-cache option when issuing 'docker build' for building the image

#### Usage
This image should be used as a base image to build a PostgreSQL container

A script named "create_database.sql" should be put at the same folder of the Dockerfile when building the image to create your database

Here is the sample of the SQL script

```sql
CREATE USER testuser WITH CREATEDB PASSWORD 'testpassword';
CREATE DATABASE testdb ENCODING 'UTF8' TEMPLATE template0 OWNER testuser;
```
