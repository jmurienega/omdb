# How to setup Postgres, Grafana and Prometheus with Docker

This docker compose will generate the following services:
* Postgres with an omdb database.
* Grafana
* Prometheus
* Postgres-exporter

_Note_: omdb (open media database) is a free database for film media. More info in https://github.com/credativ/omdb-postgresql


## Requeriments 

* Docker

### Setup
First, you will need to install [Docker](https://docs.docker.com/engine/install/).

#### Clone files
_Note_: use monitoring branch

```bash
git clone --branch monitoring git@github.com:jmurienega/omdb.git
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

#### Connect to Grafana
open http://localhost:3000
```code
User: admin
password: admin
```
##### Add Dashboard
1. Select Configuration > DataSource > Add new Data Source
    ![add server](https://res.cloudinary.com/practicaldev/image/fetch/s--OLVdfcY8--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w71n8ehokbecgwdug55q.png)
2. Save and test.

    ![add server](https://res.cloudinary.com/practicaldev/image/fetch/s--r6TcUXNU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5oqhx5d5fy1f7hfmrpon.png)
	
    _Note_: use this field to add a descriptive name for the server; the name specified will be displayed in the Browser tree control
3. Import PostgresSQL Dashboard: Select Dashboard > Import
    ![add server](https://res.cloudinary.com/practicaldev/image/fetch/s--9Tt46UMU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jt2nl7m16u5vs6acdhe8.png)
4. Configure Import Details
    ![add server](https://res.cloudinary.com/practicaldev/image/fetch/s--ipyZ_6XV--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sxay2jd25fgtgd2g9ix5.png)
5. View Dashboard
    ![add server](https://res.cloudinary.com/practicaldev/image/fetch/s--y9ZX_Prt--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nd2njnq1ans9e1mtvyal.png)
---
#### Down Services

This will remove all services with data

```bash
docker compose down --volumes
```