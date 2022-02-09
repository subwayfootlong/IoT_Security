This folder is for transmiting data from ESP8266 to HiveMQ
# Connecting to HiveMQ Securely (with certificates)
### Components used to connect the microcontroller, ESP8266 Arduino to HiveMQ 
1. NodeMCU (an ESP8266 board)
2. HiveMQ - a MQTT cloud broker, which can be used for free

### Hardware 
1. NodeMCU 

### Software
1. Arduino IDE installed on the computer
2. HiveMQ MQTT cloud broker platform, which can be used for free. It is a MQTT broker where we can create an account and connect your IOT devices. It can connect up to 100 devices.

### Steps
1. Firstly, we have to install proprietary Arduino IDE.
2. Once Arduino IDE is installed, enable support for the ESP8266 chip which will provide the WiFi functionality. To enable this, start the Arduino IDE and open the Preferences window. Add the additional board manager: https://arduino.esp8266.com/stable/package_esp8266com_index.json. Select the ESP8266 board once the above package have been added.
3. To use HiveMQ Cloud, the MQTT library need to be added first. Download the PubSubClient and add the library.
4. The next library that is required is the NTPClient. Install this library into Arduino by searching for NTPClient in the library manager. The purpose of this library is use to update the internal clock of the ESP8266 board in order to use the TLS certificates.
5. To upload certificates to our board, we must use the LittleFS Filesystem Uploader. This will help us to connect securely with HiveMQ Cloud. 
6. Next, we need to get the certificates that are needed to encrypt the connection to HiveMQ Cloud. 
7. Now, we connect our MQTT clients by uploading the code on Arduino to connect to HiveMQ Cloud instance. The code creates an MQTT client that is publishing and subscribing to a topic on our HiveMQ Cloud cluster. 

Prerequisites:
Follow this guide: https://console.hivemq.cloud/clients/arduino-esp8266?uuid=c689cd9ab0cf406bbc142988277304d9



## For ar.exe and openssl
Install the ESP8266 Board for Arduino using this guide: http://arduino.esp8266.com/Arduino/versions/2.0.0/doc/installing.html

OpenSLL configuration https://www.openssl.org

## Data
Contains the certificate needed to upload to hivemq with SSL
