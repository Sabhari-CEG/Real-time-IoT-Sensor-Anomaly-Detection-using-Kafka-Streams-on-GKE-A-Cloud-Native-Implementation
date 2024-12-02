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
