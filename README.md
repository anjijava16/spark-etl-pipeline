<h1 align="center">SPARK-ETL-PIPELINE</h1>
<h4 align="center">demo various data fetch/transform process via Spark Scala </h4>

## Prerequisites 

1. Modify [config](https://github.com/yennanliu/spark-etl-pipeline/tree/master/config) with your `creds` to be able access services like data source, file system.. and so on. 
2. Install SBT as scala dependency management tool 
3. Install Java, Spark 


## Quick Start
```bash
# STEP 0) 
$ git clone https://github.com/yennanliu/spark-etl-pipeline.git && cd spark-etl-pipeline 

# STEP 1) download the used dependencies.
$ sbt clean compile

# STEP 2) print twitter via spark stream  via sbt run`
$ sbt run

# # STEP 3) create jars from spark scala scriots 
# $ sbt assembly

```

## Quick Start (Docker)
```bash 
# STEP 0) 
$ git clone https://github.com/yennanliu/spark-scala-word-count.git

# STEP 1) 
$ cd spark-scala-word-count

# STEP 2) docker build 
$ docker build . -t spark_env

# STEP 3) ONE COMMAND : run the docker env and sbt compile and sbt run and assembly once 
$ docker run  --mount \
type=bind,\
source="$(pwd)"/.,\
target=/spark-word-count \
-i -t spark_env \
/bin/bash  -c "cd ../spark-word-count && sbt clean compile && sbt run && sbt assembly"

# STEP 3') : STEP BY STEP : access docker -> sbt clean compile -> sbt run -> sbt assembly -> spark-submit 
# docker run 
$ docker run  --mount \
type=bind,\
source="$(pwd)"/.,\
target=/spark-word-count \
-i -t spark_env \
/bin/bash 
# inside docker bash 
root@942744030b57:~ cd ../spark-word-count && sbt clean compile && sbt run 

```

## Ref 

<details>
<summary>Ref</summary>

- Stream via python socket 
	- https://pythonprogramming.net/buffering-streaming-data-sockets-tutorial-python-3/
- Install spark + yarn + hadoop via docker 
	- https://medium.com/@thiagolcmelo/submitting-a-python-job-to-apache-spark-on-docker-b2bd19593a06
	- https://www.svds.com/develop-spark-apps-on-yarn-using-docker/

</details>

## Dataset 

<details>
<summary>Dataset</summary>

- Twitch API (`stream`)
	- https://dev.twitch.tv/docs/v5/reference/streams/
- Dota2 API (`stream`)
	- https://docs.opendota.com/#section/Authentication
- NYC TLC Trip Record dataset (taxi) (`large dataset`)
	- https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page
- Amazon Customer Reviews Dataset  (`large dataset`)
	- https://registry.opendata.aws/amazon-reviews/
- Github repo dataset (`large dataset`)
	- https://www.kaggle.com/github/github-repos
- Hacker news dataset (`large dataset`)
 	- https://www.kaggle.com/hacker-news/hacker-news
- Stackoverflow dataset (`large dataset`)
	- https://www.kaggle.com/stackoverflow/stackoverflow
- Yelp dataset (`large dataset`)
	- https://www.kaggle.com/yelp-dataset/yelp-dataset
- Relational dataset (RDBMS online free dataset)
	- https://relational.fit.cvut.cz/search

</details> 