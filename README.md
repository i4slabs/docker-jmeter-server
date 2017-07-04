# docker-jmeter-server
Dockerized jmeter server and k8s recipes for deployment

### Clone repository

Clone the repo.
```
$ git clone https://github.com/i4slabs/docker-jmeter-server.git
```

Go into repo path.
```
$ cd docker-jmeter-server
```

## K8S (Kubernetes)


[Kubernetes](https://kubernetes.io) is an open-source system for automating deployment, scaling, and management of containerized applications. If you are not familiar with kubernetes see this [tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/).

### Templating
Edit the vars in the k8s/vars file:
```
NAMESPACE=namespace-dev
ENDPOINT=namespace-dev.example.com
```

Generate backend (Deployment) and service (Service and Ingress) recipes:
```
$ sh templater.sh k8s/jmeter-server-backend.tmp.yaml -f k8s/vars > k8s/jmeter-server-backend.yaml
```
```
$ sh templater.sh k8s/jmeter-server-service.tmp.yaml -f k8s/vars > k8s/jmeter-server-service.yaml
```

### Deploy

Deploy to k8s.
```
$ kubectl create -f k8s/jmeter-server-backend.yaml
```
```
$ kubectl create -f k8s/jmeter-server-service.yaml
```
