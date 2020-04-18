# [M121: The MongoDB Aggregation Framework](https://university.mongodb.com/courses/M121/about)

- [Click here to install MongoDB on system](https://docs.mongodb.com/manual/administration/install-enterprise/)

* To connect to M121 course Atlas Cluster, using the mongo shell, you will need to use the following connection command:

```
$ mongo "mongodb://cluster0-shard-00-00-jxeqq.mongodb.net:27017,cluster0-shard-00-01-jxeqq.mongodb.net:27017,cluster0-shard-00-02-jxeqq.mongodb.net:27017/aggregations?replicaSet=Cluster0-shard-0" --authenticationDatabase admin --ssl -u m121 -p aggregations --norc
```

```
Cluster0-shard-0:PRIMARY> show collections
air_airlines
air_alliances
air_routes
bronze_banking
customers
employees
exoplanets
gold_banking
icecream_data
movies
nycFacilities
silver_banking
solarSystem
stocks
system.views
```

- To check TCP connection for port 27017

```
$ curl http://portquiz.net:27017/
```

# The Concept of Pipelines

- Pipelines are the composition of stages which are configurable for transformation where documents will flow like an assembly line and can arrange in multiple ways

# Quiz

**Which of the following is true about pipelines and the Aggregation Framework?**

- **The Aggregation Framework provides us many stages to filter and transform our data**
- Stages cannot be configured to produce our desired output.
- Pipelines must consist of at least two stages.
- **Documents flow through the pipeline, passing from one stage to the next**

# Aggregation Structure and Syntax

```
$ db.collectionName.aggregate([{stage1}, {stage2}, {__stageN}], {options})

Field as varaiable: `$fieldName`
System Variable: `$$CURRENT`
User Variable: `$$foo`
```

- Pipelines are always an array of one or more stages
- Stages are composed of one or more aggregation operators or expression.
- Expression may take single argument or an array of arguments. This is expression dependent

# Quiz

**Which of the following statements is true?**

- Only one expression per stage can be used.
- **An aggregation pipeline is an array of stages.**
- **Some expressions can only be used in certain stages.**
