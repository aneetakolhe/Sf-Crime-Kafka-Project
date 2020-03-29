Question - How did changing values on the SparkSession property parameters affect the throughput and latency of the data?
Answer - It increase inputRowsPerSecond and processedRowsPerSecond values. Increase of these values lead to more data getting processed in single batch.

Q : What were the 2-3 most efficient SparkSession property key/value pairs? 
Through testing multiple variations on values, how can you tell these were the most optimal?
A: Increasing the number of cores to 20 local[20] and maxOffsetsPerTrigger to 50K, which increased the processedRowsPerSecond to 361.34.
Increasing the value of core, automatically increased spark.default.parallelism value to the same amount. In addition, increasing 
spark.streaming.kafka.maxRatePerPartition to 500 increased the inputRowsPerSecond drastically to 525.80