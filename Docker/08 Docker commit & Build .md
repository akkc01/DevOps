### Docker commit command-
- useful to commit a container's file changes or settings into a new image.

```
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```
- example-
```
docker commit my_ubuntu  akkc:version1
docker commit -a "Author Name" -m "Added new features" <container_id> <new_image_name>
```
-Options of Docker Commit

- `-a, --author`  Specifies the author name for the image
- `-c, --change`	  Applies Dockerfile instructions to the image
- `-m, --message`	  Specifies a commit message for the image
- `--pause`	  Pauses the container during commit
- `-p, --pause-file`	  Pauses the container using a pause file during commit
- `--platform`	  Sets the platform if not specified in the Dockerfile
