### Handy commands

#### start connectors
`bin/connect-standalone.sh config/connect-standalone.properties config/connect-elasticsearch-sink.properties`

#### add topic contents
`./bin/kafka-console-producer.sh --broker-list localhost:9092 --property parse.key=true --property key.separator="&" --property value.converter.schemas.enable=false --topic connect-test-2`

contents like:

```
1&{"test":"one"}
```

#### see topic contents
`bin/kafka-console-consumer.sh --topic connect-test-2 --from-beginning --bootstrap-server localhost:9092`

#### delete topic contents
first, edit `delete.json`
`bin/kafka-delete-records.sh  --bootstrap-server localhost:9092 --offset-json-file delete.json`
