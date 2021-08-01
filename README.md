# Kafka Security Overlay

## Install procedure
On all macines
Use python >3.7 for this
- create a virtualenv with python 3
- install requirements.txt (if you have errors with cryptography, update pip)

## Usage instruction

### Auth server

- cd into RestAuth
- run python3 manage.py runserver_plus --cert ./ssl/ <ip>:8000
- allow firewall access to this port
- check by accessing the website on browser. You can ignore brower warnings for now
  
### Broker overlay server
  - cd into KafkaOverlay
  - run python3 manage.py runserver <ip>:5000
  - allow firewall access to this port
  
