## Install ubuntu as docker container-

### Pull the Image-
```
Docker pull ubuntu
```

### run the ubuntu container-
```
docker run -d --name linux4 -it ubuntu bash
```
### you can also used this-
```
docker run -d --name linux25022 -it ubuntu
```
### Create multiple container-
```
for ($i = 1; $i -le 50; $i++) {
    docker run -d --name "BBPL_$i" -it ubuntu bash
}
```

### Test--
```
docker run -d --name linux4 ubuntu bash
docker run -it --name linux4  ubuntu bash
docker run --name linux4 ubuntu bash
docker run -d -it ubuntu
```
### Kill multiple container-
```
docker kill (docker ps -q)
```

### Remove/Delete multiple container-
```
docker rm (docker ps -a -q)
```
