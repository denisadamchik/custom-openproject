# Custom OpenProject installation with Docker

Clone this repository:

    git clone https://github.com/denisadamchik/custom-openproject --branch=master

Go to the project folder: 

    cd custom-openproject

To create the local directories where the data will be stored across container restarts, and start the container with those directories mounted:

    sudo mkdir -p /var/lib/custom-openproject/{pgdata,assets} 

    docker run -p 8080:80 --name custom-openproject \
     -e SERVER_HOSTNAME=customopenproject.example.com \ # The public facing host name
     -e SECRET_KEY_BASE=secret \ # The secret key base used for cookies
     -v /var/lib/custom-openproject/pgdata:/var/openproject/pgdata \
     -v /var/lib/custom-openproject/assets:/var/openproject/assets \
     denisadamchik/custom-openproject

After a while, Custom OpenProject should be up and running on <http://localhost:8080>.

You can now stop the container by running:

    docker stop custom-openproject

And start it again:

    docker start custom-openproject