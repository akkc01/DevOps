## Docker Networking-
---

### How to Create a Bridge Network-
```
docker network create -d bridge my-net
```
- it will create a bridge network name: my-net

### inspect a Network-
```
docker network inspect my-net
```
- it will shows the all the ips assigned to the container's, dns and address space of the network.
### how to cnnect a container to network-
```
docker network connect network_name container_name
```
- example-
```
docker network connect akkc ak_fire
docker network connect my-net ubuntu
```
### Connect to network at time of container creation-
```
docker run -d --name container_name --network network_name --port host_port:container_port -it nginx
```
- example-
```
docker run -d --name nginx_ak --network akkc -p 8181:80 -it nginx
docker run -d --name firefox_ak --network akkc -p 9090:3000 -it linuxserver/firefox
```
### how to install Firefox container-
```
docker pull linuxserver/firefox
docker run -dit --network network_name -p 8888:3000 linuxserver/firefox
```
- default port for `linuxserver/firefox's` is:3000

  

