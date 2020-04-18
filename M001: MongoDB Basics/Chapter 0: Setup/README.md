# [M001: MongoDB Basics](https://university.mongodb.com/courses/M001/about)

# Quiz

**What resources are available to help you complete this course?**

- **An in-class discussion forum where you can ask questions and help your fellow learners**
- **Teaching assistants to field questions and provide guidance on the course.**
- Instructor's email address

# Quiz - Grading and Logistics

**Which of the following count toward your final grade?**

- Quizzes
- **Labs (also called homework)**
- **Final exam**

---

- [Click here to download the MongoDB on to your system](https://www.mongodb.com/download-center/enterprise)

- Run the following command to start the mongo shell without connecting to any database instance after installing the MongoDB

```
$ mongo --nodb
```

- [Please confirm that port 27017 is not blocked by clicking](http://portquiz.net:27017)

- If successful, you will see a page load that indicates you can make outgoing requests on port 27017.

- Simpler test to see if you can reach Atlas

```
$ ping cluster0-shard-00-00-jxeqq.mongodb.net
```

- The class atlas cluster consists of three different nodes and you must be able to make outgoing requests to all these three nodes.

```
cluster0-shard-00-00-jxeqq.mongodb.net
cluster0-shard-00-01-jxeqq.mongodb.net
cluster0-shard-00-02-jxeqq.mongodb.net
```

- Download Compass from the [MongoDB Download Center](https://www.mongodb.com/download-center/compass)

- **Note** : Do NOT download or install the "Community Edition Stable" version, please make sure you are using the latest (Stable) version of Compass

- Launch Compass and click on the 'New Connection'

---

#### Method 1

- Paste this string in the connection string field and hit CONNECT.

```
mongodb+srv://m001-student:m001-mongodb-basics@cluster0-jxeqq.mongodb.net/test
```

- Adding this connection string as a favorite allows you to easily reconnect to MongoDB class deployment after closing and restarting Compass.

---

#### Method 2

- Click on Fill in connection fields individually:

- Hostname Tab

```
Hostname: cluster0-jxeqq.mongodb.net

Port: 27017

Authentication: Username / Password

Username: m001-student

Password: m001-mongodb-basics

Authentication Database: admin


```

- More Options Tab

```
Replica Set Name: Cluster0-shard-0
Read Preference: Primary
```

---

## Connecting to Atlas Cluster from the mongo Shell

#### Mathod 1

- SRV (Service record record) connection string

```
mongo "mongodb+srv://cluster0-jxeqq.mongodb.net/test" --username m001-student -password m001-mongodb-basics
```

#### Mathod 2

- standard connection string

```
mongo "mongodb://cluster0-shard-00-00-jxeqq.mongodb.net:27017,cluster0-shard-00-01-jxeqq.mongodb.net:27017,cluster0-shard-00-02-jxeqq.mongodb.net:27017/test?replicaSet=Cluster0-shard-0" --authenticationDatabase admin --ssl --username m001-student --password m001-mongodb-basics
```

- **Note:** '27017/test' where 'test' is the DB name, it can be znything

---

# Quiz - Connecting to Our Class Atlas Cluster from the mongo Shell

**When connecting to an Atlas cluster using the shell, why do we provide the hostnames for all nodes when we launch mongo? Choose the best answer from the choices below.**

- **So that if the primary node goes down, the shell can connect to other nodes in the cluster instead**
- To make it possible for all the nodes to communicate with each other
- So that other nodes in the cluster can contact our client, if necessary
- There really isn't a good reason
- Because our authentication credentials are not stored on the primary, but on other nodes in our cluster.

---
