This folder covers the Security Testing Portion of our Project

# Steps Taken to test security of project

We followed this [guide](https://www.cypressdatadefense.com/blog/how-to-do-security-testing-manually/) on how to do security testing on the Node-RED UI and one of the steps proved that we were able to get in.

## Brute Force Attack

| Vunerability | Security Steps Taken |  
| ----------- | ----------- |  
| Node-RED login screen was unprotected We tried the common passwords and was able to get in as the initial username: node and password: node  | Change the password to include special characters and numbers |  
| No limit to wrong password. Attackers can try to log in multiple times without the website blocking them | Notify admin when a wrong login takes place. Admin can then block that IP via oracle cloud VM console |