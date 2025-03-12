Create an alerting application using golang with the following specifications 

Transport Layer 
gRPC + Rest 

Functionality
1. An alert is something which consists of a message with media, destination, channel
   Example: Hey anonymous, your order is out for delivery by our awesome partner tony who will be reachable on 987654321.
            Please be available to collect your shipment. 
            Regards,
            Etailify 
            Destination : 99888881111
            Channel : WhatsApp
  These alerts can also be recurring alerts which trigger based on a condition and will keep on alerting the subject until the 
  condition evaluates to false. An example for this would be, product stock falling below a configured threshold in a warehouse.

 In general, along with the above specs of an alert, it will also have a retry window, backoff window, alert condition.

The goal is to make the application as generic as possible to support multiple use cases. You can assume the following channels 
for simplicity - SMS, WhatsApp. You don't have to do a realworld SMS send / WhatsApp message send, it can be a real world 
simulation as well. 

Good to haves,
UTs 
Integration Tests 
HLD document with proper reasons as to why a specific database/technology was chosen
LLD document / Swagger Specification
