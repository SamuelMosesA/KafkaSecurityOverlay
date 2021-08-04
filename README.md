# Kafka Security Overlay

## Install procedure
On all macines
Use python >3.7 for this
  * create a virtualenv with python 3
  * install requirements.txt (if you have errors with cryptography, update pip)

## Usage instruction

### Auth server
  * cd into RestAuth
  * run python3 manage.py runserver_plus --cert ./ssl/ <ip>:8000
  * allow firewall access to this port
  * check by accessing the website on browser. You can ignore brower warnings for now
  
### Broker overlay server
  * edit the ipsettings in /overlay/ipsettings.py to 
    * add the details for auth server's address and port
    * add the deatails for the kafka bootstrap server
  * cd into KafkaOverlay
  * run python3 manage.py runserver <ip>:5000
  * allow firewall access to this port
  
  
### Client
   
  * edit the ipsettings.py with the server ip port for auth and broker side server
  * run the script with python3
  * if everything is successful, it will show the prompt to type
  * the typed data will be visible in the kafka console consumer
  
  
## Admin instruction
  
  * auth server has admin portal
  * you can access it by adding going to https://<authserverip>:<port>/admin
  * login into the admin
  * to add a new user, go to the User database and create
  * if the user is a client
    * during the creation, add the *client* group to the user
    * add a public and private key for it in the KeyStore database
    * in the ACL database add the producer or consumer privileges for each topic
  * if user is a broker, add the *broker_overlay* group while creation
  
  
  
