# How to setup Docker Postgres Example Database
This is an example database for the course.
omdb (open media database) is a free database for film media. More info in 
https://github.com/credativ/omdb-postgresql
## Requeriments 

* docker
* docker-compose

## Clone this repository in local folder

```bash
git clone --branch main git@github.com:jmurienega/omdb.git
````

---

## Build and run with docker-compose
open cmd in the localfolder an run
```bash
docker-compose up
```

---
## Connect to db

```bash
* host: localhost
* database: omdb
* port: 5432
* user: root
* password: root
```

---
## Down Services

```bash
docker-compose down --volumes
```