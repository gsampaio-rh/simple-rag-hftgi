### Inference Server Setup

The inference server is responsible for performing text inference tasks using Hugging Face's Large Language Models. You need to specify the URL of the inference server that the application will communicate with.

- `INFERENCE_SERVER_URL` should be set to the URL of your Hugging Face inference server. If you're running the server locally for testing, you can use "http://localhost:3000/". For production or cloud environments, you would replace this with the actual URL of your deployed inference server.

### Kafka Setup

This application uses Kafka for message queueing, consuming messages from a chat topic, processing them, and then producing responses to an answer topic.

- `KAFKA_SERVER` specifies the address of your Kafka server. If running locally, it's typically set to "localhost:9092". For production, this would be the address of your Kafka cluster.
- `CONSUMER_TOPIC` is the name of the Kafka topic from which the application will consume messages. This should be set to "chat" or whichever topic you have designated for incoming chat messages.
- `PRODUCER_TOPIC` is the name of the Kafka topic to which the application will produce processed messages. This is set to "answer", or any other topic name where you want the processed messages to be published.

Ensure these settings are correctly configured to match your environment before running the application.