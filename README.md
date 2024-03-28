# ESP32LR20 Getting Started
The client build with an wifi and mqtt connection system, which can be set by variables in the top of the `main.cpp` file. Currently there is no implemention for `TLS`, so if this is needed, some more work has to be done.

## Build
To Build on the device, press the blue reset-button in the correct moment while uploading the new firmware.


## MQTT
The client will auto connect to the broker and reconnect if needed. It will send all 10 seconds the state, an every time the state changed or some other device is requesting the state.

List of subscribes
* esp32lr20/cmd/state
  * this will trigger the esp to send his current relay state
* esp32lr20/cmd/relay1/on
  * this will turn on the relay 1
* esp32lr20/cmd/relay1/off
  * this will turn off the relay 1
* esp32lr20/cmd/relay2/on
  * this will turn on the relay 2
* esp32lr20/cmd/relay2/off
  * this will turn off the relay 2

List of publishes
* esp32lr20/state
  * Returns an JSON with the relay state `{ "relay1":"on","relay2":"off" }`

