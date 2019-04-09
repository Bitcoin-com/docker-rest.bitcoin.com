# docker-rest.bitcoin.com
This repository contains a Dockerfile and bash shell scripts for building
a containerized version of [rest.bitcoin.com](https://github.com/Bitcoin-com/rest.bitcoin.com).

## Installation
These directions are geared at Ubuntu 18.04 OS with at least 2GB of RAM,
and a non-root user with sudo privledges. Before installing this software, you
need to have a **Bitcoin Cash Full Node** to connect
it to. All software components must be targeted for either testnet or mainnet.


* It's always a good idea to add
[swap space](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04)
to a new system. I recommend 8GB of swap typically.

* Install Docker on the host system. Steps 1 and 2 in
[this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)
shows how to install Docker on a Ubuntu system.

* Clone this repository:

`git clone https://github.com/Bitcoin-com/docker-rest.bitcoin.com && cd docker-rest.bitcoin.com`

* Create a BASH shell script for starting the server, based on the
[example script file](config/start-example). Fill in the full node IP address
and login info and the Insight server IP address. Edit the Dockerfile
to use this file. Note: If you rename the file to either `start-testnet` or
`start-mainnet` then it will not be saved to Git, thus not exposing the sensitive
credential information.

* Customize the [Dockerfile](Dockerfile) to point to either testnet or mainnet.

* Build the Docker images by running the 'build' shell script:

`./build-image`

* After the Docker image has been build, you can start it with the 'run' shell script:

`./run-image`

* You can now access the REST server at port `3003`.
