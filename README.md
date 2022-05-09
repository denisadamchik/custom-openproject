# Custom OpenProject installation with Docker Compose

## Install

Clone this repository:

    git clone https://github.com/denisadamchik/custom-openproject --branch=master

Go to the project folder: 

    cd custom-openproject

Make sure you are using the latest version of the Docker images:

    docker-compose pull

Launch the containers:

    docker-compose up -d

After a while, Custom OpenProject should be up and running on <http://localhost:8080>.

## Uninstall

You can remove the stack with:

    docker-compose down

