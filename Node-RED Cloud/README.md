# Node-RED Cloud
This section covers the main program that is using the programming environment, Node-RED.This is hosted on Oracle Virtual Cloud for free as we are not storing any data on the virtual cloud itself. It is running Oracle-Linux-7.9-2021.10.20-0.



## Security
### Steps taken to secure the vm:
- SSH key required to access VM
![image](https://user-images.githubusercontent.com/74981128/150664690-6329731f-f6e3-4614-bf25-96fd13d95c4e.png)
- Block all ports except 1880
### Steps taken to secure the Node-RED
- Enable Username and Password login

![image](https://user-images.githubusercontent.com/74981128/150667335-0a77c411-fc9d-49d6-aad2-3031794464dd.png)

Node-RED can be configured to use TLS however, this is a challenge as we are using a Virtual Machine and generating and uploading the certificates in that Virtual machine is not so straight forward. 
[Guide to create secure certificates](https://it.knightnet.org.uk/kb/nr-qa/https-valid-certificates/)

# Guides:
[Guide to get Node-RED on Cloud(FREE)](https://www.youtube.com/watch?v=TaVXyR4S2Qo)

Node-RED script installer (RPM based Linux ONLY)

`bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/rpm/update-nodejs-and-nodered)`

[Starting Node-RED on boot](https://nodered.org/docs/faq/starting-node-red-on-boot#rpm-based-linux-redhat-fedora-centos)

[Securing node-red](https://nodered.org/docs/user-guide/runtime/securing-node-red#editor--admin-api-security)



