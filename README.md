# Orchestrator-service

## How to build and push to docker
Clone repo
```
git clone https://github.com/Saga-pattern/Orchestrator-service.git
```

Go to the project
```
cd Orchestrator-service
```

Build project. Push image to docker hub
```
docker build -t orchestrator-service .
```
```
docker tag orchestrator-service <your-repo>:latest
```
```
docker push <your repo>:latest
```

## Event flow send and receive
