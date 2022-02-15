This folder is meant for connecting the microcontroller, Node-MCU to HiveMQ securely with certificates

# Connecting to HiveMQ Securely (with certificates)
## Components used to connect the microcontroller, ESP8266 Arduino to HiveMQ 
- NodeMCU (an ESP8266 board)
- HiveMQ - a MQTT cloud broker, which can be used for free


## Hardware 
- NodeMCU 


## Software
- Arduino IDE installed on the computer
- HiveMQ MQTT cloud broker platform, which can be used for free. It is a MQTT broker where we can create an account and connect your IOT devices. It can connect up to 100 devices.


## Steps
1. Firstly, we have to install proprietary Arduino IDE.
2. Once Arduino IDE is installed, enable support for the ESP8266 chip which will provide the WiFi functionality.
3. To use HiveMQ Cloud, the MQTT library need to be added first. Download the PubSubClient and add the library.
4. The next library that is required is the NTPClient. Install this library into Arduino by searching for NTPClient in the library manager. The purpose of this library is use to update the internal clock of the ESP8266 board in order to use the TLS certificates.
5. To upload certificates to our board, we must use the LittleFS Filesystem Uploader. This will help us to connect securely with HiveMQ Cloud. 
6. Next, we need to get the certificates that are needed to encrypt the connection to HiveMQ Cloud. 
7. Now, we connect our MQTT clients by uploading the code on Arduino to connect to HiveMQ Cloud instance. The code creates an MQTT client that is publishing and subscribing to a topic on our HiveMQ Cloud cluster. 


# Installation procedure for ESP8266 Arduino Core
## Steps
1. Start Arduino and open Preferences window.
2. Enter the URL into Additional Board Manager URLs field to enable the ESP8266 chip that provide the WiFi functionality: http://arduino.esp8266.com/stable/package_esp8266com_index.json
3. Once the package is added, find the esp8266 platform under the Board Manager
4. Select the version that is needed
5. Install the board
6. Once installation is done, select the ESP8266 board.


# Uploading the certificates to the board
## LittleFS Filesystem Uploader
LittleFS Filesystem Uploader is an Arduino plugin which compile sketch data folder into LittleFS filesystem image and then uploads the image to ESP8266 flash memory.

### Steps to install the plugin
1. Download the zip folder ESP8266LittleFS-2.6.0. 
2. Go to Arduino IDE directory and open the tools folder
3. Unzip the folder, copy and paste it into the Arduino IDE tools folder
4. Restart Arduino IDE and ESP8266 LittleFS Data Upload will appear on the tools bar.


# Generating the certificates
## Using OpenSSL
We are using OpenSSL to generate the certificates. OpenSSL is a common open-source command line tool to generate SSL/TLS certificates, private keys and identify certificate information. It is also used for general-purpose cryptography and to secure communication. It is free to get and can be used for commercial and non-commercial purposes as it is licensed under an Apache-style license.

## Getting the certificates that are needed for an encrypted connection to HiveMQ Cloud
### Steps
1. We will generate the certificate in Python IDE and we will execute the Python script. A file will be generated containing the certificates.
2. We move the file into the directory of Arduino IDE sketch. 
3. We then open Arduino IDE and open Tools>ESP8266 LittleFS Data Upload and this will upload the files into the board's flash memory.

# Connecting MQTT Clients
We will execute the code on Arduino IDE to connect to our HiveMQ Cloud. The code will create an MQTT client that will publish and subscribe to a topic on our HiveMQ Cloud cluster.
