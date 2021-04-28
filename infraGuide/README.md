### Linux Infra Tools Quick start Guide
It contains quick star guide for infra tools for linux.

#### <ins>Elastic Search</ins>
##### Install:
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html

##### Start/Stop:
````
sudo systemctl start elasticsearch.service
sudo systemctl stop elasticsearch.service
````

##### Sample Run:
curl -X GET "localhost:9200/?pretty"

##### Setting max size for elastic search cluster:
- By default, it takes more than 3gb of ramspace which might not be viable for local testing.
- So create a file "/etc/elasticsearch/jvm.options.d/heap.options"
- Edit it and place below text and save it.
````
-Xms1g
-Xmx1g
````
- Now start the elastic search. It will now consume approx 1gb.

#### <ins>Kibana</ins>
##### Install:
https://www.elastic.co/guide/en/kibana/current/deb.html

##### Start/Stop:
````
sudo systemctl start kibana.service
sudo systemctl stop kibana.service
````

##### Sample Run:
Open localhost:5601

#### <ins>Redis</ins>
##### Install:
````
sudo add-apt-repository ppa:redislabs/redis
sudo apt-get update
sudo apt-get Install: redis
````

##### Start/Stop:
````
redis-server
````
Stop above command to stop the server

##### Sample Run:
- Open Redis Cli to run commands
````
redis-cli
````
- Once it opens, you can run below commands:
````
ping
set mykey somevalue
get mykey
````

#### <ins>Confluent Kafka in Docker</ins>
##### Install:
https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.html

##### Start/Stop:
````
Go to folder containing docker-compose.yml file
docker-compose up -d
docker-compose stop
````

##### Removing all stopped containers
Older containers need to be removed as there might be errors like "The container name "/zookeeper" is already in use by container". In this scenario you can use below command to remove old containers.
````
docker container prune
````

##### Status check
````
docker-compose ps
````

##### Sample Run:
Open http://localhost:9021