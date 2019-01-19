
### Goals
This project intends to implement Kafka and Spark streaming. A few objectives:

- Integrate Kafka and Spark
- Compare between Sparkstreaming and Spark micro batching
- Conduct ETL and store in parquet / Cassandra


### Contexts
I became interested in broadening spark experience and related tech stacks around it.
I was inspired from https://www.youtube.com/watch?v=y3O94MnO_IU and https://www.youtube.com/watch?v=wQfm4P23Hew

Uber's data platform has transformed from

![alt text](/images/uber_past.png)

to 

![alt text](/images/uber_present.png)

Changes have reduced data latency from 24 hours to < 1hr. 



### Steps for this repo

1. Kafka -> SparkStreaming (ETL) -> Parquet


![alt text](/images/spark_kafka.png)


2. Comparing performances of Microbatching and Streaming
![alt text](/images/spark_stream_microbatch.png)

Prior to May 2018, SparkStreaming had more of concept of micro batching. As you create you had to set batching time with desired intervals.

```
val ssc = new StreamingContext("local[*]", "PrintTweets", Seconds(1))
```

But with Spark 2.3, Spark offers realtime streaming. For details, it can be found https://databricks.com/blog/2018/03/20/low-latency-continuous-processing-mode-in-structured-streaming-in-apache-spark-2-3-0.html




3. Connect spark with Cassandra
![alt text](/images/cassandra.png)



