## Kafka on Kubernetes

K8s deploymenys + services for Apache Zookeeper, Apache Kafka and the kafka UI manager.

## Kubernetes (minikube)

Prerequisities for minikube:
* `brew install hyperkit`
* `brew install minikube`

Start the minikube cluster
* `minikube start --vm-driver=hyperkit`

Verify cluster exists and ready:
* `kubectl get nodes`

Apply stack:
* `kubectl apply -f zookeeper-deployment.yml`
* `kubectl apply -f kafka-broker-deployment.yml`
* `kubectl apply -f kafka-manager-deployment.yml`

Get our k8s url for our manager service in our minikube cluster
* `minikube service kafka-manager`

```
|-----------|---------------|-------------|---------------------------|
| NAMESPACE |     NAME      | TARGET PORT |            URL            |
|-----------|---------------|-------------|---------------------------|
| default   | kafka-manager |        9000 | http://192.168.64.2:30594 |
|-----------|---------------|-------------|---------------------------|
🎉  Opening service default/kafka-manager in default browser...
```

After going to the kafka manager, add the cluser:

`zookeeper-service:2181`

and click save.

## License

Copyright © 2021 Tyler Hoersch

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.