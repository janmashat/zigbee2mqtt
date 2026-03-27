This is just a simple environment with:

* zigbee2mqtt: a bridge from zigbee (through a zigbee USB stick) to MQTT
* mosquitto: an MQTT server
* ~~home assistant: a home automation platform, with MQTT support.~~ 
~~zigbee2mqtt also supports auto discovery for home assistant.~~ (disabled for now)

You'll need to configure zigbee2mqtt with a `z2m-data/configuration.yaml` file.
There is an onboarding web interface that is quite convenient, but I have disabled it .
Just comment out the appropriate line (`Z2M_ONBOARD_NO_SERVER=1`) or create your own file like so:

```
homeassistant: true
permit_join: true
mqtt:
  base_topic: zigbee2mqtt
  server: 'mqtt://mqtt' # The mosquitto server in this case.
serial:
  port: /dev/ttyACM0  # The serial device. It should be the same as the device entry in docker-compose.yml.
```

More info here: http://balkian.com/controlling-zigbee-devices-with-mqtt.html
