# VeChain Local Development Stack

__Adresses:__

VeChain node swagger: http://localhost:8669/

VeChain web3-gear: http://localhost:8545/

## DockerCompose


Simple run in docker-compose mode.

```
docker-compose up
```
You can expect some warnings during running this command. In docker-compose.yml we have swarm configuration, but it doesn't affect normal compose mode.


Docker compose stop command

```
docker-compose down
```




## Swarm mode

To have better scalability and failover in local development we can use swarm mode

First we have to init swarm

```
docker swarm init
```

Next we have to deploy our stack

```
docker stack deploy --compose-file docker-compose.yml initdemo
```
initdemo is our stack name

If you don't have both images downloaded locally, first start in swarm mode can take a quite long time, especially for web3-gear.

### Useful commands:

Stop local swarm node
```
docker swarm leave --force
```

List running services
```
docker service ls
```


```
docker stack ps <GROUP_NAME>
```
