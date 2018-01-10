# React-Webpack-Rails-Docker-Compose
A boiler plate for quickly building Rails API applications with React+Webpack frontend in containerised enviornment and is deployment ready for production.
This application consists of a frontend folder which contains the user facing pages in React and a backend folder which is in Rails serving the API.

# Services
  - Rails 5 API backend application
  - Postgres database
  - React+Webpack for Client side application

# Backend App
This is the API written in Rails 5

# Frontend App

# Running the Application
It is recommended to install [Docker compose](https://docs.docker.com/compose/install/#install-compose) on your machine.

- Build the entire application,
    ```sh
    $ docker-compose build
    ```
- Build single service,
    ```sh
    $ docker-compose build service_name
    ```
- Boot the application,
    ```sh
    $ docker-compose up
    ```
    Check Containers are running,
    ```sh
    $ docker-compose ps
    ```
    Assuming application containers are runnning properly,
    For Backend API, you can navigate to it at http://localhost:3050
    For Frontend, you can navigate to it at http://localhost:8080

- Open up a bash to Backend application
    ```sh
    $ docker-compose run --rm backend bash
    ```
- Open up a bash to Frontend application
    ```sh
    $ docker-compose run --rm --service-ports frontend bash
    ```
    The --service-ports flag is passed so that while running bash, we can hit the app at port 8080 from our web browser.
- Run Rails console
    ```sh
    $ docker-compose run backend rails console
    ```
- Database creation and migration
    ```sh
    $ docker-compose run backend rake db:create db:migrate
    ```


# Additions Required
  - Nginx proxy to avoid cross origin issues
