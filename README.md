# project-description
Behooked is an open source webhooks service that allows clients to register webhooks for one or more events. Upon successful registration, clients will receive a notification each time the event occurs. 

- The Webhook API allows you to administrate webhooks. 

- The Trigger API allows you to administrate triggers and thus define for which type of events you would like to offer a webhook.

- The Event API allows you to receive event notifications from a source system.

  - A kafka-connector is available for you to receive event notification from a Kafka cluster.
  
  <br>
  <br>
  <img src="/sw_architecture.jpg" alt="sw_architecture_behooked" title="Behooked's Software Architecture">
  
  
1. Rgister a new webhook

2. Connector listens for event_X

3. Connector informs administration-service that event_X occured

4. Dispatcher-Service stores event_X in database 

5. Dispatcher-service requests clientdata for all webhooks that are registered for event_X

6. Administration-Service returns clientdata

7. Dispatcher-Service sends an event notification to registered clients

In the diagram the source system is based on Apacha Kafka and thus the Behooked Kafka Connector is used as an adapter. It is also possible that the source system sends an event notification directly via HTTP call.


