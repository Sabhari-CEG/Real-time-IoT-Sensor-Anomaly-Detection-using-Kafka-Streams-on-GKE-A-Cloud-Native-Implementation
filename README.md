# Real-time-IoT-Sensor-Anomaly-Detection-using-Kafka-Streams-on-GKE-A-Cloud-Native-Implementation
A high-performance, cloud-native solution for real-time anomaly detection in IoT sensor networks using Apache Kafka on GKE. This project demonstrates advanced streaming data processing by implementing two distinct approaches: a traditional line-by-line method and an optimized KSQL stream processing solution,achieving a 25x performance improvement. 

Key Features:
• Cloud-native deployment on GKE with Kafka clusters
• Real-time anomaly detection for temperature, humidity, and voltage readings
• Scalable data pipeline processing 2.3M+ records
• Performance optimization from 6.3 hours to 10-15 minutes processing time
• Implementation of both traditional and KSQL stream processing approaches (Dual implementation approach)

Anomaly Detection Parameters:
1. Temperature: > 100° or < 0°
2. Humidity: < 0% or > 100%
3. Voltage: < 1.5V or > 3.0V

Performance Metrics
1. Line-by-line processing: 6.3 hours for 2.3M records
2.  KSQL stream processing: 10-15 minutes for 2.3M records
3.  Per record processing time: ~8-14ms (line-by-line)

Technologies: Kubernetes, Apache Kafka, KSQL, Google Cloud Platform, Shell Scripting

The implementation began with deploying Apache Kafka in Google Cloud Platform's Kubernetes Engine using the available marketplace image. I configured the deployment with essential parameters including namespace configuration (default), storage class (premium-rwo), and resource allocations for both Kafka (10Gi) and ZooKeeper (5Gi) instances. The deployment resulted in a fully functional Kafka cluster consisting of kafka-check-kafka-0 pod for the broker, kafka-check-kafka-exporter for metrics collection, and kafka-check-zk-0 for ZooKeeper coordination.

Following the cluster setup, I established a data pipeline for processing sensor readings. The pipeline began with uploading our dataset containing 2.3 million temperature, humidity, light, and voltage readings to a GCP bucket. I then implemented a streaming mechanism using kubectl commands to transfer data from the GCS bucket to our Kafka cluster. The data ingestion process utilized Kafka's console producer with the command kubectl exec, streaming data through the kafka-check-kafka-headless:9092 broker to a dedicated topic named 'sensor_data'.

As we spin up the GKE, we first check its status,

![pod check](initial_pod_check.png)

We then Upload our source data to GCP buckets

![bucket](data.png)

Now we create a new topic and check whether the topic is created succesfully

![topic](topic.png)

Now we set up the data pipeline from GCP buckets to kubernetes pods

![image](pipeline1.png)

![image](pipeline1.png)
