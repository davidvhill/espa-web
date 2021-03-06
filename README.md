# espa-web

This project is the ESPA website implemented with angular.js, bootstrap 3, and Docker.  It relies on the espa-api to interact with user orders and information.

### Install Docker
Visit `https://www.docker.com/`

### Clone this repository
`git clone https://github.com/dhill-usgs/espa-web.git espa-web`

`cd espa-web`

### Build the Docker image
`docker build -t espa-apache2 .`

### Run the Docker container (development mode)
`docker run -it --rm -p 8888:80 -v $PWD/htdocs:/usr/local/apache/htdocs --name espa-website espa-apache2`

This will allow you to continue working on the site in htdocs without rebuilding the image.

Just be sure to commit any changes before going into production!

### Run the Docker container (operational mode)

`docker run -it -d -p 8888:80 --name espa-website espa-apache2`

### View the site
Open `http://localhost:8888` in a browser

### Notes
`bin/run_dev.sh` and `bin/run_daemon.sh` will handle building and running the docker images for you.

If you started the container as a daemon, you can interact with it:

View logs: `docker logs espa-website`

Connect via terminal: `docker exec -it 'espa-website' bash`

Stop the container: `docker stop espa-website`

And verify it is stopped: `docker ps`

Start it again: `docker start espa-website`

Or remove it and start fresh: `docker rm espa-website`

And finally delete the image from your machine: `docker rmi espa-apache2`






