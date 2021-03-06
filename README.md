# Kafka Streams workshop
## Prerequisites 
1. Install docker, CE (Community Edition). The installation instructions for Linux, Mac and Windows you can find [here](https://docs.docker.com/install/)
2. Install docker compose [here](https://docs.docker.com/compose/install/).
3. Verify the installation. Run *docker* , *docker-compose* commands from your terminal
4. In our workshop we're going to use Twitter API for the real-time data. So everyone should generate API keys and token to access the API.

   Go to this [link](https://apps.twitter.com/app/new) (You need to be logged into your twitter account) Follow the instructions. 
   
   - In *Website* tab you can put any site URL, e.g. https://developer.twitter.com/
   - In *Callback URLs* click on *Add a Callback URL* button
   - Click on *Generate your Twitter application* button
   - Go to the *Keys and Access Tokens* tab and click on *Create my access tocken* button
   
   After this process you supposed to have 4 keys: 
   + API KEY (Consumer key)
   + API secret (Consumer secret)
   + Access token
   + Access token secret
   
   Save them in safe place on your laptop. We'll use all of them later on.
   
 5. In addition to Twitter API we'll use [this API](https://www.alphavantage.co/) for real-time stock data
 
    Open this link above and click on *Get your free API key today*. 
    
    Follow the instructions and get the key and save it.
    
    
 ## Docker Compose
 In this workshop we'll use docker-compose to create our dockerized development environment.
 
 docker-compose will start all required containers for this workshop: Kafka and Zookeeper conatiners.
 
 + git clone this repo
 + cd to  *./docker* folder
 + *docker-compose up -d*
 + check the docker are up and running : *docker ps*
 
 + In order to get into Kafka container, run :
   *docker exec -i -t container-id /bin/bash*
 + Check if all Kafka topics have been created properly :
 
       docker ps
       docker exec -i -t zk-container-id /bin/bash
       ifconfig  (take ZK IP)
       docker exec -i -t kafka-container-id /bin/bash
       $KAFKA_HOME/bin/kafka-topics.sh --list --zookeeper zk-IP
       
  It should print list of topics like that : 
  
       outputtopic1
       outputtopic2
       outputtopic3
       twitters
   
   
 
 
 
     
   
