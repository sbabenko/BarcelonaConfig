# Docker Compose Setup for Angular and .NET Backend

This project contains a Docker Compose setup for an Angular front-end and a .NET backend using SignalR. 

## Prerequisites

- Docker installed on your machine
- Docker Compose installed

## Project Structure

Ensure your project has the following structure:

/YourProjectRoot
|-- /BarcelonaFrontEnd
|   |-- src
|   |   -- Dockerfile
|   -- package.json
|-- /BarcelonaBackEnd
|   -- Dockerfile
|-- docker-compose.yml

## Starting the Application

To start the application, navigate to the directory containing the docker-compose.yml file and run:

docker-compose up

This command will build the images for both the front-end and back-end services and start the containers.

### Accessing the Application

- Angular Frontend: [http://localhost:4200](http://localhost:4200)
- .NET Backend: [http://localhost:5209](http://localhost:5209)

## Stopping the Application

To stop the application and remove the containers, run:

docker-compose down

### Remove Volumes (Optional)

If you want to also remove the associated volumes, use:

docker-compose down --volumes

### Rebuild Without Cache (Optional)

If you need to rebuild your images without using the cache, use:

docker-compose build --no-cache

## Common Troubleshooting

If you see the default Nginx page instead of your Angular application, ensure:

1. The build process is successful.
2. The correct output directory is specified in the Dockerfile.
3. The Angular app files are present in the Nginx directory (/usr/share/nginx/html).

### Inspecting Logs

To check the logs of your services, run:

docker-compose logs

## Cleanup

To remove all stopped containers and unused images, you can run:

docker system prune
