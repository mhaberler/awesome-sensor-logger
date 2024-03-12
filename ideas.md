# Theengs BLE decoder integration

This could be done in a separate process on the broker host which 
- subscribes to BLE sensor data published by sensorlogger
- decodes the BLE adds
- publishes ads
```mermaid
graph TD;
    Sensorlogger--publish-->MQTT_Broker;
    MQTT_Broker --subscribe to 
    raw BLE ads-->Theengs_Decoder;
    Theengs_Decoder --publish decoded 
    sensor data-->MQTT_Broker;
    Consumer--subscribe to
    decoded data-->MQTT_Broker;
```
