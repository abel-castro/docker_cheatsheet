Selection of docker commands for working with python/django projects.


## Basics
| Description | Command |
|-------------|---------|
| Build containers | `docker-compose build` |
| Builds, (re)creates and starts containers | `docker-compose up` |
| Up containers in daemon mode | `docker-compose up -d` |
| Up + build | `docker-compose up --build` |
| Stop and remove containers | `docker-compose down` |
| Start containers | `docker-compose start` |
| Stop containers (without removing them)| `docker-compose stop` |
| Show containers | `docker ps -a` |                
| Remove all stopped containers | `docker container prune` |                
| Remove all unused containers, volumes and images | `docker system prune` |                


## Interact with containers
| Description | Command |
|-------------|---------|
| Start a container and allow breakpoints* on it | `docker-compose run --rm --service-ports <service_name>` |
| Run commands inside a containers | `docker-compose run --rm <container_name> <command>`|
| Open shell in a container | `docker-compose run --rm <container_name> sh` |


\* Python breakpoints in python with pdb are not working if you are using  `docker-compose up`.


## Images
| Description | Command |
|-------------|---------|
| List all available images | `docker images` |
| List all images used by the created containers | `docker-compose images`|
| Remove a image | `docker rmi <image_name>` |
| Remove dangling** images | `docker image prune` |

\** A dangling image volume is one that is not tagged and is not referenced by any container.

## Volumes
| Description | Command |
|-------------|---------|
| List all volumes | `docker volume ls` |
| Remove a volume | `docker volume rm <volume_name>`|
| Remove all unused volumes | `docker volume prune`|


## Docker registry
| Description | Command |
|-------------|---------|
| Login in https://hub.docker.com | `docker login` |
| Login in other registry | `docker login <registry_url>` |
| Pull images for the services defined in docker-compose.yml | `docker-compose pull` |
| Push images for the services defined in docker-compose.yml | `docker-compose push` |
