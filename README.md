# Docker Commands
#### Grouping most of the basic docker commands in a clean and simple markdown. All of these commands are found in the official docs. However, I am grouping here those I use the most for faster reach. &nbsp;

### Exploring running containers and images  &nbsp;

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker ps`         | docker ps groups exposed ports into a single range. Can display container ID, name,  date created, port, etc.. This command will only list running containers not the stopped ones. |
|` docker ps --help`  | wil list down all flags that can be used with docker ps. |
|` docker run --help`  | wil list down all flags that can be used with docker run. |
| `docker ps --a`     | wil list down all containers including those stopped |
| `docker ps --aq`    | wil list down all containers ids (only ids) including those stopped |
| `docker container ls`| wil list down all containers. |
| `docker container --help` | wil list down all flags that can be used with docker container. |
| `docker image --help` | wil list down all flags that can be used with docker image. |
| `docker image ls` | wil list down all images pulled. |
| `docker image ls` | wil list down all images pulled. |


### Formatting output

| Command             |     				  	 			  						                                  
| ------------------- |
| ` docker ps --format="ID\t{{.ID}}\nNAME\t{{.Names}}\nImage\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Command}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n `|


### Pulling and running images with exposing ports in different scenarios 

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker pull image_name ` | pull an image. |
| `docker run image_name:tag ` | run a container from an image. can add '-d' before the image name to run in detached mode. |
| `docker run -d -p 8080:80 image_name:tag ` | run a container from an image in detached mode, with exposing it to local port 8080. Use -p to expose to as many ports as you need. |
| `docker run --name container_name image_name:tag ` | run a container with an exact name. Can inspect the name using `docker ps -a`. Other flags can be included. |


### Stopping, removing and starting containers

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker stop container_id ` or ` docker stop container_name` | Only stops a container but does not remove it. |
| `docker remove container_id ` or ` docker remove container_name` | Removes a stopped container. Won't work if it is running |
| `docker rm $(docker ps -aq) ` | Remove all stopped containers. Will break if there are any running containers. It can be forced to remove running containers by `-f` flag |


### Creating volumes in different scenarios 

| Command             | Description    				  	 			  						                                  
| ------------------- |:-------------------------------------------------|
| `docker run --name container_name -v ${pwd}:/usr/share/nginx/html:ro -d -p 8080:80 image_name:tag ` | Create a volume between the host machine and container. Must `cd` till the project root directory. This will be in read only mode, which can be removed by removing `:ro`.  If we have a file inside the container, it will also appear in our host |
| `docker exec -it container_name bash` | execute in interactive mode, pass the container name, and excute the bash command |
| `docker ps --name container_name_2 --volume-from container_name_1 -d -p 8081:80 image_name:tag` | volumes between containers, add --volume-from container_name_1 after the container_name_2 name to create a volume between two containers|
