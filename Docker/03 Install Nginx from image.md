## Install the nginx using docker-
### Search the image from dockr hub using-
- Docker search <image_name>
```powershell
Docker search nginx
```
-choose the 1s one nginx.
### Pull the Image from docker hub to local PC using-
- Docker pull <image_name>.
```powershell
Docker pull nginx
```
### Run the nginx-
```powershell
 docker run -d nginx
```
- run nginx in detached mode-
```powershell
 docker run -d nginx
```
### Rename the name of nginx instance-
- replace the name akkc as your need.
```powershell
docker run -d --name akkc nginx
```

## To Run the 50 instances of nginx-
- run this command using Power Shell 7.x.x OR from Bash-
```powershell
for ($i = 1; $i -le 50; $i++) {
    docker run -d --name "nginx_instance_$i" nginx
}
```
