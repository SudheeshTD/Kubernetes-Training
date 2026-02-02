There will be app

and a Dockerfile(file) in this directory.

that Docker file will have info about the application and how to install it and run it from ground up.

then you need to build this docker file witeh a Tag: `docker build . -t voting-app`

this creates a docker image of that application.

then you can run the docker image using the command: `docker run -d -p 5000:80 voting-app` (That port 80- will be mapped to 5080).

You can chedk the new image by running `docker images` command.

Also to link the redis to this application you can use the command: `docker run -p 5000:80 --link redis:redis voting-app`

DO the same for all the services you have to run.
----Build a app first using the docer file
----Then run the app using docker run command.
---Link the services using --link command.
-- the once all the services are running you can access the application using localhost:5000

Once you hav built all the containers you can create a docker-compose.yml file to run all the containers using a single command.

use the command: `docker-compose up -d` to run all the containers in detached mode.

Create a persisting volume for redis using the command: `docker volume create <Volume-Name>`

then use that volume in the docker-compose file to persist the data.

to run the container with the volume use the command: `docker run -d  -v <Volume-Name>:/data --name redis redis:alpine`
where /data is the path inside the container where redis stores its data.
2 types of volumes:

- 1. Named Volume: creates a volume that is managed by Docker and can be reused across multiple containers.
- 2. Bind Mounts: maps a directory on the host(our system) to a directory in the container.

Use Mount command to mount a volume.: command: `docker run -d --mount type=bind,source=<Host_location>,target=<ContainerLocation> --name <container-name> <image-name>`

# To push a docker image to docker hub use the following commands:

1. `docker login` (to login to your docker hub account)
2. `docker tag <image-id> <dockerhub-username>/<repository-name>:<tag>` (to tag the image)
3. `docker push <dockerhub-username>/<repository-name>:<tag>` (to push the image to docker hub)

We can then pull the image from docker hub using the command: `docker pull <dockerhub-username>/<repository-name>:<tag>`
