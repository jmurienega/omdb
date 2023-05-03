# How to setup Postgres Docker

This docker compose will generate the following services:
* Postgres with an postgres_air database.

_Note_: postgres_air database can be used for training and various performance experiments. More info in https://github.com/hettie-d/postgres_air


## Requeriments 

* Docker

### Setup
First, you will need to install [Docker](https://docs.docker.com/engine/install/).

#### Clone files

```bash
git clone --branch tuning git@github.com:jmurienega/omdb.git
````

Download https://drive.google.com/file/d/1blDNnM0rgDkudUZLN8Y1T7Z_RfwW_l9w in the folder where you cloned the repository 

---

#### Build and run services
open cmd in the folder where you cloned the repository an run
```bash
docker compose up
```

---
#### Connect to db

```bash
host: localhost
database: postgres_air
port: 5432
user: postgres
password: postgres
```

---
#### Down Services

This will remove all services with data

```bash
docker compose down --volumes
```