# efk-docker
Repo to deal with dockerized version of efk stack

Elasticsearch is basically an open source search engine, wherein kibana makes elasticsearch query results friendly for users. 
By running elasticsearch with fluentd and kibana, we get a scalable log collection and pipeline analysis mechanism through docker. 

In this docker-compose file, we use a httpd server container for log generation, fluentd to collect the logs and forward to elasticsearch, kibana to create a visual representation of it. 

Use of logging driver, in fluentd is a design decision. All of the logs from web container will be automatically forwarded to host:post specified by the fluentd address in the docker-compose file. 

# Test Setup

Run curl command, to generate some logs, that can be targeted at the httpd server
``` repeat 10 curl http://localhost:80/ ```

Go on to localhost:5601 with your browser, to confirm logs. 

Here, you can setup an index pattern, specifically fluentd-*. 
