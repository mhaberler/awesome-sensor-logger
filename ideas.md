
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
