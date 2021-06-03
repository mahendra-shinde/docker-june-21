# Docker SWARM

* A Container orchestrator, provides HA cluster for containerized application.
* Provides Self Healing and Scaling for applications


## Check Swarm Mode

$ docker info

## Deploying a compose file on swarm

```yaml
version: "3.5"

services:
    w1:
        image: mahendrshinde/myweb:1
        deploy:
            replicas: 2
        ports: 
        - 80

    w2:
        image: mahendrshinde/myweb:2
        deploy:
            replicas: 2
            resources:
                # Max Resources
                limits:
                    cpus: '0.50'
                    memory: 50M
                # Initial assignment of resources
                reservations:
                    cpus: '0.25'
                    memory: 20M
        ports: 
        - 80
        depends_on: 
        - w1
```

$ docker stack deploy app1 -f docker-compose.yaml
$ docker stack ls
$ docker stack ps app1