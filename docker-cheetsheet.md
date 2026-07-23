- Container RUN
  docker run -it/-d -p <image name>

- To go inside the container
  docker exec -it <container_id> bash

- Bind mount your folder on a container: 
  docker run -d -p --mount type=bind,src=<host_folder>,dst=<container_folder_jis_per_mount_karna_hai> <image_name>

- Volumes:  
  docker volume create
  -v volume_name:/path
  
- Image Build: 
  docker build -t name:tag . , The . at the end is the build context
  COPY . . copies everything from host to container
  FROM — base image
  RUN — execute commands during build
  COPY — copy files from host to image
  WORKDIR — set working directory
  EXPOSE — document the port
  CMD — default command
  
  Nginx serves files from /usr/share/nginx/html/

- SQL Container Command
  docker run -d -p 3307:3306 -v mysql_volume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=mysqlroot mysql
  docker exec -it <container_id> bash
  bash5.1# mysql -u root -p

- Networks
  docker network connect <NETWORK_NAME> <CONTAINER_NAME_OR_ID>
  Ping on the default bridge: docker exec [CONTAINER ID/nginx] ping [OTHER CONTAINER IP/mysql]
  
   

  
