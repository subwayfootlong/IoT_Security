# IoT_Security
This repository covers a project required by a module named IoT security, which focuses on using IoT technologies securely.

## Project description
### Theme
Secured End-to-End IoT for Car Parking System
### Flowchart
![image](https://user-images.githubusercontent.com/74981128/153140988-9e5425e4-c95b-4a40-b07e-123997550ea1.png)
### Explanation
To create a Secure End-to-End IoT Car Park System, we decided to create a door/gantry that would only allow authorized users to log in. Users have to login with their correct username and password into the Cloud hosted Node-RED UI then they will receive 2 Factor Authentication key on Telegram by a Bot we programmed. They then have to input the 2FA key into the Node-RED UI and if it is correct, the gantry/door will then open. Their username will also be logged in the cloud service InfluxData database.

## Folders
| Files | Description |  
| ----------- | ----------- |  
| Node-RED Cloud | Cloud hosted Node-RED instance to process and input data |  
| Notification | Node-RED to telegram for notification and 2 factor Authentication |
| Connecting | Connecting Node-MCU to HiveMQ securely |
| Visualize | Node-RED to InfluxDB cloud to visualize the entry timing of users |


## Change Log
### January 2022
- 18 Node-MCU to HiveMQ connection Established 
- 19 Node-MCU to HiveMQ with SSL connection Established 
- 20 Node-RED online server Live
- 21 Node-RED to InfluxDB SSL connection Live
- 22 Telegram Notification Live
- 26 Node-RED password secured
- 28 2FA function live

### Febuary 2022
- 1 Version 1.0 Live
- 9 Github README.md fully updated 
