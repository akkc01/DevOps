### Docker commit command-
- useful to commit a container's file changes or settings into a new image.

```
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```
- example-
```
docker commit my_ubuntu  akkc:version1
```
- Options of Docker Commit

- Option	        Description
- `-a, --author`  Specifies the author name for the image
- `-c, --change`	  Applies Dockerfile instructions to the image
- `-m, --message`	  Specifies a commit message for the image
- `--pause`	  Pauses the container during commit
- `-p, --pause-file`	  Pauses the container using a pause file during commit
- `--platform`	  Sets the platform if not specified in the Dockerfile
