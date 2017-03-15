> This project settles down a ELK stack in docker swarm mode.

## Prerequisite
* A docker swarm cluster with several nodes;
* Some nodes with lable app_role=elasticsearch, try this on manager node:  
```
docker node update --label-add app_role=elasticsearch <node-id>
```


## How to use
1. Build three images: elasticsearch, logstash, kibana;
2. Push them to your docker hub;
3. Try this on manager node:  
```
docker stack deploy -c elk-stack.yml elk
```
4. Scale the elastic search cluster by add more worker and add the 'app_role=elasticsearch'label.

## TODO
![elk-stack](https://cloud.githubusercontent.com/assets/14900974/23948152/b2b2f546-09bc-11e7-8339-9a3f4e32ce4b.png)
