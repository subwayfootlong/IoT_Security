# Node-RED Cloud
This section covers the main program that is using the programming environment, Node-RED.This is hosted on Oracle Virtual Cloud for free as we are not storing any data on the virtual cloud itself. It is running Oracle-Linux-7.9-2021.10.20-0.



## Security
### Steps taken to secure the vm:
- SSH key required to access VM
- Block all ports except 1880
![image](https://user-images.githubusercontent.com/74981128/150664690-6329731f-f6e3-4614-bf25-96fd13d95c4e.png)
### Steps taken to secure the Node-RED
- Enable Username and Password login
![image](https://user-images.githubusercontent.com/74981128/150667335-0a77c411-fc9d-49d6-aad2-3031794464dd.png)


# Guides:
[Guide to get Node-RED on Cloud(FREE)](https://www.youtube.com/watch?v=TaVXyR4S2Qo)

Node-RED script installer (RPM based Linux ONLY)

`bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/rpm/update-nodejs-and-nodered)`

[Starting Node-RED on boot](https://nodered.org/docs/faq/starting-node-red-on-boot#rpm-based-linux-redhat-fedora-centos)

[Securing node-red](https://nodered.org/docs/user-guide/runtime/securing-node-red#editor--admin-api-security)



