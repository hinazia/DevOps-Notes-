## DOCKER COMMANDS

### Container RUN

  - docker run -it/-d -p <image name>

### To go inside the container

  - docker exec -it <container_id> bash/sh

### Bind mount your folder on a container: 

  - docker run -d -p --mount type=bind,src=<host_folder>,dst=<container_folder_jis_per_mount_karna_hai> <image_name>

### Volumes:  

  - docker volume create
  - -v volume_name:/path
  
### Image Build: 

  - docker build -t name:tag . , The . at the end is the build context
  - docker biuld -f <particular name dockerfile> -t <image name> .
  - COPY . . copies everything from host to container
  - FROM — base image
  - RUN — execute commands during build
  - COPY — copy files from host to image
  - WORKDIR — set working directory
  - EXPOSE — document the port
  - CMD — default command
  
  - Nginx serves files from /usr/share/nginx/html/

### SQL Container Command

  - docker run -d -p 3307:3306 -v mysql_volume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=mysqlroot mysql
  - docker exec -it <container_id> bash
     bash5.1# mysql -u root -p

### Networks

  - docker network connect <NETWORK_NAME> <CONTAINER_NAME_OR_ID>
  - Ping on the default bridge: docker exec [CONTAINER ID/nginx] ping [OTHER CONTAINER IP/mysql]

### Docker Compose

   - docker compose up --build, without --build, Docker may keep using the old image that does not contain your app file.
   - docker compose down -v , stopped and removed all services, volumes, networks etc
   - docker compose build <image_name> , to build a specififc image in dockercompose yml
  
### Docker Multi Stage Build

  - docker build --target builder -t my-builder . --> to choeck the builder stage
  - docker run -it --rm my-builder sh   ---> insode builder to debug with linux commands
  - docker compose build --no-cache webapp
    Without --no-cache: Docker sees old COPY layer → reuses it → old files remain
    With --no-cache: Docker copies everything again → new image is created

### Adding USER and GROUP when using SLIM images

  - RUN groupadd -r appgroup && \
    useradd -r -g appgroup appuser
  - USER appuser

### Adding USER and GROUP when using ALPINE images

  - RUN addgroup -S appgroup && \
    adduser -S appuser -G appgroup
    
  - find /app -name "*.html"
    Search file inside container 
    
  ### Application Logs live

    - docker compose logs .f
    - docker compose logs -f <service_name>

  ### Image Upload to Docker Hub

      - Login: docker login
      - Tag: docker tag local-image:tag username/repo:tag
      - Push: docker push username/repo:tag
      - docker pull <image_name>
      
---

  > **Note:** for a simple single-container app, Docker Hub pull is enough. For your 3-service application, Compose is the missing piece.
  

