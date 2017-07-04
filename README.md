# docker-jmeter-server
Dockerized jmeter server and k8s recipes for deployment

### Clone repository

```
$ git clone https://github.com/i4slabs/docker-jmeter-server.git
```

### K8S templating

```
$ cd docker-jmeter-server
$ sh templater.sh -f k8s/example-vars k8s/jmeter-server-backend.tmp.yaml > jmeter-server-backend.example.yaml
```
