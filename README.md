# ModemAutoReboot
An Arduino sketch for ESP8266 that detects when my internet is down and resets the modem.

## Why?
My ISP's modem will occasionally disconnect, and doesn't reconnect on its own. Unfortunately it needs to be power cycled when this happens.

## What does it do?
This sketch will connect to the access point of your choice, then wait 180 seconds (default) for the modem to boot. It then pings 8.8.8.8 every 10 seconds with a configurable timeout. If the ping times out 5 times in a row, the modem will be rebooted. It counts total failures (reboots) and logs to the serial monitor.

## Instructions
### What you need
- ESP8266
- A relay (3.3v or 5v)

1. Configure the sketch. At the very least, you need to set the SSID and password used to connect to the access point.
2. Plug the relay into the ESP8266, making sure you connect the signal pin to the one specified in the sketch (D1 default). I use a 5v relay with 3.3v no problem, but I can't say all relays will behave the same.
3. Select the correct board and COM port in the Tools tab, and flash it. Open serial monitor to see if it connects properly and make sure it pings.
4. If everything appears to work, you can now figure out a way to wire up the relay to the modem's power source. One option is to use an old power bar or extension cord and run it's positive wire through the relay.
5. Should be good to go
