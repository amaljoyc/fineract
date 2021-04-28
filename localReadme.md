# local build setup

### Requirements
* Java >= 11 (adopt OpenJDK HS JVM)
* MySQL 5.7 (using amd64 image for the apple silicon)

### bootRun and docker-compose

* bootRun for the fineract backend run
```
./gradlew bootRun
```

* docker-compose for the dependencies - mysql and mifos-ui
* mysql data is persisted in the host machine (inside the repo) under `volume/mysql-data`
```
docker compose up

# for cleanup
docker compose down
```

### k8s
* tested on a local docker-desktop cluster
* runs the fineract backend as well as the dependencies - mysql and mifos-ui
* mysql data is persisted inside the k8s node under `/mnt/fineract-data`
```
cd kubernetes
./kubectl-startup.sh

# for cleanup
./kubectl-shutdown.sh
```