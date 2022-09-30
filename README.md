# python-flask-docker
Basic Python Flask app in Docker which prints the hostname and IP of the container


```

### Run the container
Create a container from the image.
```
$ docker run --name my-container -d -p 8080:8080 bnktch/web
```

Now visit http://localhost:8080
```
 The hostname of the container is 6095273a4e9b and its IP is 172.17.0.2. 
```

### Verify the running container
Verify by checking the container ip and hostname (ID):
```
$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
172.17.0.2
$ docker inspect -f '{{ .Config.Hostname }}' my-container
6095273a4e9b
```
# Run in k8s
To run in k8s you are going to create a deployment and a service

$ kubectl create deployment.yaml

