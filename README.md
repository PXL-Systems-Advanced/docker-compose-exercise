# docker-compose-exercise
This is a Docker compose exercise made for the Capgemini Engineering Docker workshop.

## Project structure
### Database
A MySQL database consisting of one table with some movies (see database/database.sql).

### Webapp
The webapp retrieves the movies from the database and shows them in a HTML page. This webapp is build using Flask (a Python Microframework).

## Exercise
## 1. Running the database and webapp
First create a separate network for the database and webapp by running: `docker network create --driver bridge docker-compose-exercise`

Start the containers by running:
* Database: `docker run -d --name database --net=docker-compose-exercise -e MYSQL_ROOT_PASSWORD=movie123 pxlsystemsadvanced/docker-compose-exercise-database`
* Webapp: `docker run -d --name webapp --net=docker-compose-exercise -p 8082:80 pxlsystemsadvanced/docker-compose-exercise-webapp`

Open your browser and go to http://localhost:8082. You will now see the movies from the database displayed by the webapp.

## 2. Running with Docker Compose
To run the containers you had to execute 3 commands. It would be easier if we only had to execute one command. We can achieve this by using Docker Compose.

### Creating a compose.yml
Create a `compose.yml` file to run the webapp and the database. Information on how to create such a file can be found here:

Once your created the `compose.yml` file, run:
```
docker compose up
```
