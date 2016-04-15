# Docker Datacenter demo

## Preparation
```
docker-machine create -d virtualbox slave
eval $(docker-machine env slave)
```

## Run Demo App

```
docker-compose -f voting-app/docker-compose.yml up -d
```

## Verify

**Find the virtual machine ip where docker daemon is running:**
```
docker-machine ip slave
```
**Access the voting and result applications with your browser:**
```
http://$IP:5000
http://$IP:5001
```

## Shutdown
```
docker-compose -f voting-app/docker-compose.yml down -v
```

## Cleanup

**Remove the docker-machine slave:**
```
docker-machine rm -f slave
```
