# Simple Docker Nginx and Docker Setup

## System Requirements
- Docker cli
- Docker compose extension

## How to start
- Simply execute `docker-compose up` or `docker-compose up -d` for detached mode.
- Now you can visit [http://localhost:8000](http://localhost:8000) to see the changes up and running.
- and `docker-compose down` can be used to stop the container.

## Working
  - It will first refer to the `docker-compose.yml` file and setup the services.
  - There are two services that we are using here:
    - PHP using PHP:alpine image
    - Nginx using Nginx:alpine image
  - It copies the files in the current directory to `/var/www/html` directory
  - It also sets the root directory of Nginx to `/var/www/html` so that the files in current directory are hosted with Nginx
  - The Nginx Dockerfile also updates the contents of Nginx Configuration file with the contents from file default.conf so that it can execute and serve PHP files.

## Caveats
  - Right now, if you make changes in the files it will not reflect in the container, for that you can add volumes section to the `docker-compose.yml` file