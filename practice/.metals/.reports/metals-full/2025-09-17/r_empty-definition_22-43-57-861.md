error id: file://<WORKSPACE>/02_retail_data.scala:`<none>`.
file://<WORKSPACE>/02_retail_data.scala
empty definition using pc, found symbol in pc: `<none>`.
empty definition using semanticdb
empty definition using fallback
non-local guesses:
	 -scala/Predef.
	 -scala/Predef#
	 -scala/Predef().
offset: 171
uri: file://<WORKSPACE>/02_retail_data.scala
text:
```scala
import org.apache.spark.sql.SparkSession

val spark = SparkSession.builder()
  .appName("Aggregating Retail")
  .getOrCreate()

val retailDF = spark.read.format("csv").opt@@ion("header", "true").option("inferSchema", "true").load("../data//retail-data/by-day/*.csv")
```


#### Short summary: 

empty definition using pc, found symbol in pc: `<none>`.