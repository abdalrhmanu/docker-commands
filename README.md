# Docker Commands
#### Grouping most of the basic docker commands in a clean and simple markdown. All of these commands are found in the official docs. However, I am grouping here those I use the most for faster reach. &nbsp;

### Exploring running containers and images  &nbsp;

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker ps`         | docker ps groups exposed ports into a single range. Can display container ID, name,  date created, port, etc.. This command will only list running containers not the stopped ones. |
|` docker ps --help`  | wil list down all flags that can be used with docker ps. |
| `docker ps --a`     | wil list down all containers including those stopped |
| `docker ps --aq`    | wil list down all containers ids (only ids) including those stopped |
| `docker container ls`| wil list down all containers. |
| `docker container --help` | wil list down all flags that can be used with docker container. |
| `docker image --help` | wil list down all flags that can be used with docker image. |
| `docker image ls` | wil list down all images pulled. |
| `docker image ls` | wil list down all images pulled. |

### Pulling and running images with exposing ports in different scenarios 

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker pull image_name ` | pull an image. |
| `docker run image_name:tag ` | run a container from an image. can add '-d' before the image name to run in detached mode. |
| `docker run -d -p 8080:80 image_name:tag ` | run a container from an image in detached mode, with exposing it to local port 8080. Use -p to expose to as many ports as you need. |
| `docker run --name someName image_name:tag ` | run a container with an exact name. Can inspect the name using `docker ps -a`. Other flags can be included. |


