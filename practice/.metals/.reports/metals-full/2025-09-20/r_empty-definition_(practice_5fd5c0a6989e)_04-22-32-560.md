file://<WORKSPACE>/02_retail_data.scala
empty definition using pc, found symbol in pc: 
semanticdb not found
empty definition using fallback
non-local guesses:

offset: 1344
uri: file://<WORKSPACE>/02_retail_data.scala
text:
```scala
// Not functional code

import org.apache.spark.sql.SparkSession

spark.conf.set("spark.sql.shuffle.partitions", "5")

val retailDF = spark.read.format("csv").option("header", "true").option("inferSchema", "true").load("../data/retail-data/by-day/*.csv")

retailDF.show()

retailDF.printSchema()

import org.apache.spark.sql.functions.date_format

val pDF = retailDF.na.fill(0).withColumn("day_of_week", date_format($"InvoiceDate", "EEEE")).coalesce(5)

pDF.show()

val Array(trainingData, testData) = pDF.randomSplit(Array(.7,.3), seed = 42)

import org.apache.spark.ml.feature.{StringIndexer, OneHotEncoder, VectorAssembler}

val indexer = new StringIndexer().setInputCol("day_of_week").setOutputCol("day_of_week_index")
val onehot = new OneHotEncoder().setInputCol("day_of_week_index").setOutputCol("day_of_week_onehot")

val vectorAssembler = new VectorAssembler().setInputCols(Array("UnitPrice", "Quantity", "day_of_week_onehot")).setOutputCol("features")

import org.apache.spark.ml.Pipeline

val transformationPipeline = new Pipeline().setStages(Array(indexer, onehot, vectorAssembler))

val fittedPipeline = transformationPipeline.fit(trainingData)

val transformedTraining = fittedPipeline.transform(trainDataFrame)

import org.apache.spark.ml.clustering.KMeans

val kmeans = new KMeans().setK(20)
val kMeansModel = kmeans.fit(transfor@@medTraining)

kMeansModel.computeCost(trans)
```


#### Short summary: 

empty definition using pc, found symbol in pc: 