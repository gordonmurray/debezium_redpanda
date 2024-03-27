# CDC using Debezium and RedPanda

Start the containers:

```
docker-compose up -d
```

Connect to the Debezium container:


```
docker exec -it debezium /bin/bash
```

Create a Connector in Debezium:

```
curl -X PUT http://localhost:8083/connectors/my_database/config -H "Content-Type: application/json" -d @connector.json
```

List Connectors:

```
curl localhost:8083/connectors
```

Check Connector status:

```
curl localhost:8083/connectors/my_database/status
```


The UI for RedPanda Console will be available at http://localhost:8080

You'll see some topics created in the UI, such as `testing.mydatabase.products-value`
