### How to build the package

- sbt clean package
- mkdir jars
- cp target/scala-2.12/main-scala-chapter3_2.12-1.0.jar jars/

### How to run the Example

#### Standalone job submission
* spark-submit --class main.scala.chapter3.Example3_7 jars/main-scala-chapter3_2.12-1.0.jar ../../datasets/blogs.json

####  job submission in yarn cluster
* spark-submit --class org.apache.spark.examples.SparkPi \
    --master yarn \
    --deploy-mode cluster \
    --driver-memory 4g \
    --executor-memory 2g \
    --executor-cores 1 \
    --queue thequeue \
    jars/main-scala-chapter3_2.12-1.0.jar \
    ../../datasets/blogs.json
