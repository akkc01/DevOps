## Install the nginx using docker-
### Search the image from dockr hub using-
- Docker search <image_name>
```powershell
Docker search nginx
```
- choose the 1st image of nginx.
### Pull the Image from docker hub to local PC using-
- Docker pull <image_name>.
```powershell
Docker pull nginx
```
### Run the nginx-
```powershell
 docker run nginx
```
- run nginx in detached mode-
```powershell
 docker run -d nginx
```
### Rename the name of nginx instance-

```powershell
docker run -d --name akkc nginx
```
- replace the name akkc as your need.

### Port Mapping-
```powershell
 docker run -i -t --name webapp 80:80 nginx
```






## To Run the 50 instances of nginx-
- run this command using Power Shell 7.x.x OR from Bash-
```powershell
for ($i = 1; $i -le 50; $i++) {
    docker run -d --name "nginx_instance_$i" nginx
}
```
