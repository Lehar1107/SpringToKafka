# SpringToKafka

SPRING BOOT AS A PRODUCER AND KAFKA AS A CONSUMER

SPRING BOOT TO KAFKA
INSTALL APACHE KAFKA
INSTALL ECLIPSE
CREATE NEW PROJECT IN SPRING INITIALIZR ADD DEPENDENCIES “WEB”, “KAFKA”
ADD APPLICATIONS

/*
spring.kafka.consumer.bootstrap-servers: localhost:9092
spring.kafka.consumer.group-id: group-id
spring.kafka.consumer.auto-offset-reset: earliest
spring.kafka.consumer.key-deserializer: org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.consumer.value-deserializer: org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.producer.bootstrap-servers: localhost:9092
spring.kafka.producer.key-serializer: org.apache.kafka.common.serialization.StringSerializer
spring.kafka.producer.value-serializer: org.apache.kafka.common.serialization.StringSerializer
server.port=8082

*/

IF YOUR SERVER IS BUSY 8080 CHANGE PORT TO 8082
GO TO FILDER WHERE KAFKA IS EXTRACTED 

![image](https://github.com/Lehar1107/SpringToKafka/assets/126607616/de6ce94e-9667-46ea-b04b-493497a56c69)

 
OPEN COMMAND LINE
RUN FIRSTLY ZOOKEPPER
     zookeeper-server-start.bat ..\..\config\zookeeper.properties
OPEN SECOND CMD AT THE SAME PLACE
RUN KAFKA SERVER  
     kafka-server-start.bat ..\..\config\server.properties

OPEN THIRD CMD AT THE SAME PLACE
       topic-my-topic(ek topic ka name create kr diya)
       kafka-topics.bat --create --topic javaguides --bootstrap-server localhost:9092 --replication-factor 1 --partitions 3

AS YOU CAN SEE IN APP CONSTANTS HERE TOPIC NAME IS DEFINED
RUN THE SPRING BOOT APPLICATION CHECK YOUR KAFKA SERVER IS IN RUNNING MODE
THE GO TO LOCAL HOST

   ![image](https://github.com/Lehar1107/SpringToKafka/assets/126607616/5942a456-4b9a-4c3f-a07b-26701421eecc)

TYPE THE MESSAGE WHAT YOU WANT TO SEND I HAVE SEND HII IN STRING MODE
//http://localhost:8082/api/v1/kafka/publish?message=”hii”
NOW RUN ANOTHER CMD AND PASTE THIS CONSUMER
kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic javaguides --from-beginning

   ![image](https://github.com/Lehar1107/SpringToKafka/assets/126607616/4490381e-e470-4761-93cb-531bbcb104a7)

YOU CAN SEE THE OUTPUT HERE IN CMD hii
I HAVE SEND TWO MORE MESSAGE THAT’S WHY IT IS SHOWING

  ![image](https://github.com/Lehar1107/SpringToKafka/assets/126607616/4d782504-58ed-4605-a8c2-cf7b9dc7250a)
 
YOU CAN CHECK RECENT MESSAGE IS hii SEND BY THE SPRING BOOT

SPRING BOOT WORK AS A PRODUCER MESSAGE GENRATER AND YOU CONSUMER IS KAFKA YOU CAN SEE THE MESSAGE


