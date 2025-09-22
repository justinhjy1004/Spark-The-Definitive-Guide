file://<WORKSPACE>/02_retail_data.scala
empty definition using pc, found symbol in pc: 
semanticdb not found
empty definition using fallback
non-local guesses:
	 -printSchema.
	 -printSchema#
	 -printSchema().
	 -scala/Predef.printSchema.
	 -scala/Predef.printSchema#
	 -scala/Predef.printSchema().
offset: 293
uri: file://<WORKSPACE>/02_retail_data.scala
text:
```scala
// Not functional code

import org.apache.spark.sql.SparkSession

spark.conf.set(""spark.sql.shuffle.partitions", "5"")

val retailDF = spark.read.format("csv").option("header", "true").option("inferSchema", "true").load("../data/retail-data/by-day/*.csv")

retailDF.show()

retailDF.printSche@@ma()



```


#### Short summary: 

empty definition using pc, found symbol in pc: 