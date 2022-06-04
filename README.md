# SAM32WiFiEsp

With an ESP8266 board, WiFiEsp library allows an Arduino board to connect to the internet.
It can serve as either a server accepting incoming connections or a client making outgoing ones.
The WiFiEsp library is very similar to the Arduino [WiFi](http://www.arduino.cc/en/Reference/WiFi) and [Ethernet](http://www.arduino.cc/en/Reference/Ethernet) libraries, and many of the function calls are the same. 

Supports ESP SDK version 2.2 and above (AT version v3.4 and above).

**This is a fork**: this library is a fork of https://gitlab.com/Enrico204/sam32wifiesp/ which is in turn a fork of [WiFiEsp](https://github.com/bportaluri/WiFiEsp). This fork adds support for SAM32 based microcontrollers, such as Arduino 101, Arduino Due and others.
This version is has only been tested on the Raspberry Pi Pico with an ESP-01 module running the v3.4 firmware https://docs.espressif.com/projects/esp-at/en/release-v2.2.0.0_esp8266/AT_Command_Set/index.html

## Features

- APIs compatible with standard Arduino WiFi library.
- Use AT commands of standard ESP firmware (no need to flash a custom firmware).
- Support hardware and software serial ports.
- Configurable tracing level.
- Supports Arduino 101, Due and others SAM32, Pi Pico

## Wiring

The WiFiEsp library has been designed to work with the [ESP WiFi shield](http://www.instructables.com/id/Cheap-Arduino-WiFi-Shield-With-ESP8266/).
It is a cheap version of the Arduino WiFi shield that uses an ESP-01 module to provide networking capabilities to Arduino boards.


## Examples

- [ConnectWPA](https://github.com/bportaluri/WiFiEsp/blob/master/examples/ConnectWPA/ConnectWPA.ino) - Demonstrates how to connect to a network that is encrypted with WPA2 Personal
- [WebClient](https://github.com/bportaluri/WiFiEsp/blob/master/examples/WebClient/WebClient.ino) - Connect to a remote webserver 
- [WebClientRepeating](https://github.com/bportaluri/WiFiEsp/blob/master/examples/WebClientRepeating/WebClientRepeating.ino) - Make repeated HTTP calls to a webserver 
- [WebServer](https://github.com/bportaluri/WiFiEsp/blob/master/examples/WebServer/WebServer.ino) - Serve a webpage from the WiFi shield 
- [WebServerAP](https://github.com/bportaluri/WiFiEsp/blob/master/examples/WebServerAP/WebServerAP.ino) - Serve a webpage from the WiFi shield starting a local Access Point
- [WebServerLed](https://github.com/bportaluri/WiFiEsp/blob/master/examples/WebServerLed/WebServerLed.ino) - Turn on and off a led from a webpage
- [UdpNTPClient](https://github.com/bportaluri/WiFiEsp/blob/master/examples/UdpNTPClient/UdpNTPClient.ino) - Query a Network Time Protocol (NTP) server using UDP


## Supported APIs

Most of the standard Arduino WiFi library methods are available. Refer to the [WiFi library page](http://www.arduino.cc/en/Reference/WiFi) for more details.

### WiFiEsp class

- begin() - Not all authentication types
- disconnect() - YES
- config()
- setDNS() - NO (no AT command available)
- SSID() - YES
- BSSID() - YES
- RSSI() - YES
- encryptionType() - NO (no AT command available)
- scanNetworks() - YES
- getSocket()
- macAddress() - YES


### WiFiEspServer class

The WiFiEspServer class creates servers which can send data to and receive data from connected clients (programs running on other computers or devices).

- WiFiEspServer() - YES
- begin() - YES
- available() - YES
- write() - YES
- print() - YES
- println() - YES


### Client class

The WiFiEspClient class creates clients that can connect to servers and send and receive data.

- WiFiEspClient() - YES
- connected() - YES
- connect() - YES
- write() - YES
- print() - YES
- println() - YES
- available() - YES
- read() - YES
- flush() - YES
- stop() - YES


### WiFiEspUDP class

The UDP class enables UDP message to be sent and received.

- WiFiUDP - YES
- begin() - YES
- available() - YES
- beginPacket() - YES
- endPacket() - YES
- write() - YES
- parsePacket() - YES
- peek()
- read() - YES
- flush()
- stop()
- remoteIP() - YES
- remotePort() - YES


## Contributing

Probably best to contribute to the upstream projects. I just needed something that worked and hope this also helped you complete your projects.
