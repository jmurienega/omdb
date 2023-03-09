# How to setup Postgres and Pgadmin with Docker

This docker compose will generate the following services:
* Postgres with an omdb database.
* PgAdmin

_Note_: omdb (open media database) is a free database for film media. More info in https://github.com/credativ/omdb-postgresql


## Requeriments 

* Docker

### Setup
First, you will need to install [Docker](https://docs.docker.com/engine/install/).

#### Clone files

```bash
git clone --branch main git@github.com:jmurienega/omdb.git
````

---

#### Build and run services
open cmd in the folder where you cloned  the repository an run
```bash
docker compose up
```

---
#### Connect to db

```bash
host: localhost
database: omdb
port: 5432
user: root
password: root
```
---

#### Connect to pgadmin
open http://localhost:5050/
```code
email: admin@admin.com
password: root
```
##### Connect to postgres
1. Click Servers > Create > Server to create a new server.
![add server](https://miro.medium.com/v2/resize:fit:720/format:webp/1*loUwEWAVFv2J15aVIVTFoA.png)
2. set name in general tab.
![add server](https://miro.medium.com/v2/resize:fit:640/format:webp/1*KUQi0CFe1ZDHjOjOQWahJQ.png)
_Note_: use this field to add a descriptive name for the server; the name specified will be displayed in the Browser tree control
3. set values in connection tab (password: root).
![add server](https://miro.medium.com/v2/resize:fit:640/format:webp/1*BVTYvUuaWDnEgHHLQxF4Ug.png)
4. click on save

---
#### Down Services

This will remove all services with data

```bash
docker compose down --volumes
```