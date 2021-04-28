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
docker-compose up -d
docker-compose stop
````

##### Status check
````
docker-compose ps
````

##### Sample Run:
Open http://localhost:9021