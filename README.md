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
### Order created -> Reserve product
Listen to events from the topic "create-order". When there is a new event will forward that event to the topic "reserve-product".

### Product cancelled -> Reject order
Listen to events from the topic "product-cancel". When there is a new event will forward that event to the topic "reject-order".

### Product reserved -> Process payment
Listen to events from the topic "product-reserved". When there is a new event will forward that event to the topic "process-payment".

### Payment processed -> Approve order
Listen to events from the topic "payment-processed". When there is a new event will forward that event to the topic "approve-order".

### Payment cancelled -> Update product, Reject order
Listen to events from the topic "cancel-payment". When there is a new event will forward that event to the topic "product-update" and topic "reject-order".

