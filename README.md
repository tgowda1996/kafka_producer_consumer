# kafka_producer_consumer

In this project I have a kafka producer and a consumer. The system is built to process images and convert it into grayscale images. This system is scalable.

The producer monitors the input directory and on the arrival of a new image it sends the image path as a message to the topic - messages. The consumer consumes messages from this topic and converts this image into greyscale and writes it to output_image_dir.

We can have multiple producers and consumers.

The system requires the following to be installed: 
- python kafka client - pip3 install kafka-python
- opencv - pip3 install opencv (update your pip3)

Before running the producer and consumer the broker and zookeeper needs to be run:
- bin/zookeeper-server-start.sh config/zookeeper.properties
- bin/kafka-server-start.sh config/server.properties

Also the topic messages needs to be created:
- bin/kafka-topics.sh --create --topic messages --bootstrap-server localhost:9092
