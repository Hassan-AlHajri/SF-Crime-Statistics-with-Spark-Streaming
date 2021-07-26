# SF-Crime-Statistics-with-Spark-Streaming
# Step # 1
The first step is to build a simple Kafka server.
![image](https://user-images.githubusercontent.com/44734353/126999282-86fef4cd-cef0-428d-8e12-127e9a6f4f16.png)

# Step # 2
build a Kafka consumer
![image](https://user-images.githubusercontent.com/44734353/127000037-f7d70273-497a-4192-8bfa-e410c2b8ad1e.png)
![image](https://user-images.githubusercontent.com/44734353/127000181-37dcfd8d-3077-4dd2-b093-7b55ec9706e0.png)

# Step # 3
## How did changing values on the SparkSession property parameters affect the throughput and latency of the data?
The Spark Session properties allow to trade-off throughput and latency.
In some cases there was some latency due to the Spark Session properties that allow trade-off throughput and latency.
maxOffsetsPerTrigger limits on the maximimum number of offsets processed per trigger interval.
maxRatePerPartition is the maximum rate at which data will be read from each Kafka partition.
by changing the above values, we can achieve a better trade-off for throughput and latency.

## What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?
These are the best 2 options for me.
option("maxOffsetPerTrigger", 400)
option("maxRatePerPartition", 800)
after trying multiple values I got the best trade-off for throughput (can be measured in processedRowsPerSecond) and latency (in durationMs), the above 2 values gave me the best results

