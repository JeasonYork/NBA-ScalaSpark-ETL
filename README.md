# NBA-ScalaSpark-ETL
The purpose of this project is to create an ETL using Spark to extract data from the NBA API, then data will be transformed: 
API: https://new.balldontlie.io/

Key: f8b20969-dc81-4df5-8f66-2ca12b1ea771

## Project Architecture
### Create a build.sbt file with the following dependencies:

requests: to query the API

ujson: to read the content of the API response

os-lib: to create your directories and write json files to them

spark-sql: to instantiate a Spark session

### Create the following directories:

src/main/scala/ which will contain your Scala programs

games/ which will contain your json files about the matches

stats/ which will contain your json files about the stats after the matches

csv/ which will contain your final csv files

Write functions!

Use RELATIVE paths to manage your files!


## Commands to execute in the root directory:

Command to compile and package the project:
```bash
sbt package
```

Run the Extract.scala script to extract the data:
```bash
spark-submit --class "Extract" --master local[2] --packages com.lihaoyi:requests_2.12:0.1.8,com.lihaoyi:ujson_2.12:0.7.1,com.lihaoyi:os-lib_2.12:0.9.3 target/scala-2.12/nba_2.12-1.0.jar
```

To run the application, use sbt run to execute both scripts: Extract and then Transform:
```bash
sbt run
```
