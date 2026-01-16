# docker-spark-shell
Docker compose with spark-shell


### How to use it

### Create a data folder: In the same directory as your YAML file, create a folder named data. This is where you can put CSVs or scripts you want Spark to see.

### Launch the container:
```
Bash

docker-compose up -d
```
###  Attach to the shell: Since the spark-shell is interactive, you need to "join" the session to type commands:
```    
Bash

docker attach spark_interactive
```