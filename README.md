# EIEI
```
curl -X POST \
     -H "Content-Type: application/json" \
     --data '
     {"name": "mongo-sink",
      "config": {
         "connector.class":"com.mongodb.kafka.connect.MongoSinkConnector",
         "connection.uri":"mongodb://mongo1:27017/?replicaSet=rs0",
         "database":"quickstart2",
         "collection":"topicData",
         "topics":"quickstart.sampleData",
         "change.data.capture.handler": "com.mongodb.kafka.connect.sink.cdc.mongodb.ChangeStreamHandler"
         }
     }
     ' \
     http://connect:8083/connectors -w "\n"
 ```
