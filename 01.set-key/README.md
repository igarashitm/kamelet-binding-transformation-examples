# set-key transformation

- Use the quickstart for https://strimzi.io/quickstarts/ and follow the minikube guide.

- If camel-k has been installed in a specific namespace different from the default one, you'll need to add a parameter to all the commands (`-n <namespace_name>`)

- Run the following commands

      kubectl apply -f flow-binding.yaml -n kafka

- Send a JSON message to the kafka `source-topic` topic
```json
{ "field1": "kafka-key", "field2": "foo", "field3": "bar" }
```
- Check logs

      kamel logs set-key

You will see the second log shows that the header `kafka.KEY` is set to `kafka-key`.