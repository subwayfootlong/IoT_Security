This folder covers the Security Testing Portion of our Project

# Steps Taken to test security of project

We followed this [guide](https://www.cypressdatadefense.com/blog/how-to-do-security-testing-manually/) on how to do security testing on the Node-RED UI and one of the steps proved that we were able to get in.

## Brute Force Attack

| Vunerability | Security Steps Taken |  
| ----------- | ----------- |  
| Node-RED flow screen was unprotected |  Setup Login to acess Node-RED screen |
| We tried the common passwords and was able to get into the Node-RED flow screen | Change the password to include special characters and numbers |
| No limit to wrong password in User Interface. Attackers can try to log in multiple times without the website blocking them | Notify admin when a wrong login takes place. Admin can then block that IP via oracle cloud VM console |

# TR64 Compliance Checklist

The purpose of TR64-2018 standard is a guideline to safeguard our Internet of Things system. It will help us identify and mitigate threats and vulnerabilities. Below is the compliance checklist that we adhered to:

## Attack Surface 1: Web Application 
Checklist:
- TR64: IA-01 (Client and server credentials are stored securely for example; hashed or encrypted)
    - Certificates for encrypted connection to broker
    
      We generate certificates that are needed for an encrypted connection to the MQTT broker, HiveMQ Cloud. The self signed certificates to implement SSL uses X.509 Certificate
      Authority. User credentials like password are not saved in plaintext.

- TR64: RS-03 (System should be able to withstand malicious attacks such DDoS)
    - Data sent over secure protocols

      We serve the Web Application using HTTPS protocol which is more secure than HTTP.
      
## Attack Surface 2: Web Server
Checklist:
- TR64: AP-02 (Multi-factor authentication should be employed for impactful operations)
    - Secure login using 2FA 
       
       Users login with their respective username and password. They will then receive their 2FA to input into the Node-Red Cloud User Interface.
