### Linux Infra Tools Tips
It contains tips to install/start/stop infra tools.

#### Elastic Search
##### Install
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html

##### Start/Stop
````
sudo systemctl start elasticsearch.service
sudo systemctl stop elasticsearch.service
````

##### Sample Run
curl -X GET "localhost:9200/?pretty"

#### Kibana
##### Install
https://www.elastic.co/guide/en/kibana/current/deb.html

##### Start/Stop
````
sudo systemctl start kibana.service
sudo systemctl stop kibana.service
````

##### Sample Run
Open localhost:5601

#### Redis
##### Install
````
sudo add-apt-repository ppa:redislabs/redis
sudo apt-get update
sudo apt-get install redis
````

##### Start/Stop
````
redis-server
````
Stop above command to stop the server

##### Sample Run
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

#### Confluent Kafka in Docker
##### Install
https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.html

##### Start/Stop
````
docker-compose up -d
docker-compose stop
````

##### Status check
````
docker-compose ps
````

##### Sample Run
Open http://localhost:9021