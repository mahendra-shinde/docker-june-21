# Docker SWARM

* A Container orchestrator, provides HA cluster for containerized application.
* Provides Self Healing and Scaling for applications
* No Installation (built with docker)
* Do not support other container runtimes (as of now)


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

## docker-playground demo

1. Visit `https://labs.play-with-docker.com` and login with your docker-hub credentials.

2. Click 'start' button and then use "Config" button (one with wrench icon) and choose "3 Managers and 2 Workers" combo

3. Click on "Manager 1"

4. run following commands to test 

$ docker info
$ docker node ls
$ touch docker-compose.yaml

5. Use "Editor" button to copy following lines inside docker-compose.yaml file

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
        ports: 
        - 80
        depends_on: 
        - w1
```

6. Now, use following commands to deploy

$ docker stack deploy app1 -f docker-compose.yaml
$ docker stack ls
$ docker stack ps app1

7. Now, delete one of node where one of container is running (use "Delete" button)

8. Just re-run "docker stack ps app1" again on one of manager node, few times!

