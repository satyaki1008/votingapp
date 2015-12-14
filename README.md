Example Voting App
==============

This is an example Docker app with multiple services. It is run with Docker Compose and uses Docker Networking to connect containers together.

More info at https://blog.docker.com/2015/11/docker-toolbox-compose/

Architecture
-----

* A Python webapp which lets you vote between two options
* A Redis queue which collects new votes
* A Java worker which consumes votes and stores them in…
* A Postgres database backed by a Docker volume
* A Node.js webapp which shows the results of the voting in real time

Running
-------

Since this app makes use of Compose's experimental networking support, it must be started with:

    $ cd vote-apps/
    $ docker-compose --x-networking up -d

The app will be running on port 5000 on your Docker host, and the results will be on port 5001.

Docker Hub images
-----------------

Docker Hub images for services in this app are built automatically from master:

 - [docker/example-voting-app-voting-app](https://hub.docker.com/r/docker/example-voting-app-voting-app/)
 - [docker/example-voting-app-results-app](https://hub.docker.com/r/docker/example-voting-app-results-app/)
 - [docker/example-voting-app-worker](https://hub.docker.com/r/docker/example-voting-app-worker/)
