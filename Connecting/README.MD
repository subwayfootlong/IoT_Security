This folder is for transmiting data from ESP8266 to HiveMQ
# Connecting to HiveMQ Securely (with certificates)
## Components used to connect the microcontroller, ESP8266 Arduino to HiveMQ 
1. NodeMCU (an ESP8266 board)
2. HiveMQ - a MQTT cloud broker, which can be used for free

## Hardware 
1. NodeMCU 

## Software
1. Arduino IDE installed on the computer
2. HiveMQ MQTT cloud broker platform, which can be used for free. It is a MQTT broker where we can create an account and connect your IOT devices. It can connect up to 100 devices.

## Steps
1. Firstly, we have to install proprietary Arduino IDE.
2. Once Arduino IDE is installed, enable support for the ESP8266 chip which will provide the WiFi functionality.
3. To use HiveMQ Cloud, the MQTT library need to be added first. Download the PubSubClient and add the library.
4. The next library that is required is the NTPClient. Install this library into Arduino by searching for NTPClient in the library manager. The purpose of this library is use to update the internal clock of the ESP8266 board in order to use the TLS certificates.
5. To upload certificates to our board, we must use the LittleFS Filesystem Uploader. This will help us to connect securely with HiveMQ Cloud. 
6. Next, we need to get the certificates that are needed to encrypt the connection to HiveMQ Cloud. 
7. Now, we connect our MQTT clients by uploading the code on Arduino to connect to HiveMQ Cloud instance. The code creates an MQTT client that is publishing and subscribing to a topic on our HiveMQ Cloud cluster. 

## Installation procedure for ESP8266 Arduino Core
### Steps
1. Start Arduino and open Preferences window.
2. Enter the URL into Additional Board Manager URLs field to enable the ESP8266 chip that provide the WiFi functionality: http://arduino.esp8266.com/stable/package_esp8266com_index.json
3. Once the package is added, find the esp8266 platform under the Board Manager
4. Select the version that is needed
5. Install the board
6. Once installation is done, select the ESP8266 board.

## Uploading the certificates to the board
1. Download the zip folder ESP8266LittleFS-2.6.0. 
## Guide ar.exe and openssl
Install the ESP8266 Board for Arduino using this guide: http://arduino.esp8266.com/Arduino/versions/2.0.0/doc/installing.html

OpenSLL configuration https://www.openssl.org
