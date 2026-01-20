# docker-spark-shell
Docker compose with spark-shell


## How to use it
Create a data folder: In the same directory as your YAML file, create a folder named data. This is where you can put CSVs or scripts you want Spark to see.

## Launch the container:
```
Bash

docker-compose up -d
```
## Check cluster status
- Spark Master UI -> http://localhost:8080
- Worker UI -> http://localhost:8081
- Spark History UI -> http://localhost:18080
- JupyterLab -> http://localhost:8888

## Run spark-shell (Scala)
```
docker exec -it spark-master /opt/spark/bin/spark-shell \
  --master spark://spark-master:7077 \
  --conf spark.eventLog.enabled=true \
  --conf spark.eventLog.dir=/opt/spark/events
```
## Run spark-submit
```
docker exec -it spark-master /opt/spark/bin/spark-submit \
  --master spark://spark-master:7077 \
  --conf spark.eventLog.enabled=true \
  --conf spark.eventLog.dir=/opt/spark/events \
  your_app.jar
```
## Verify Logs Are Written
```
docker exec -it spark-master ls /opt/spark/events
```

## Clear the Spark shell console at any time:
```
:reset
```

