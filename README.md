# DevOps-Workshop-Infra

This is the official repo for the DevOps Workshop platform.
*The slides used are included in this repo [here](https://github.com/sergioandresmeneses/DevOps-Workshop-Infra/blob/master/Docs/slides.pdf)*

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them


 * Vagrant - check the following link for further details: [Install](https://www.vagrantup.com/docs/installation/).
 * VirtualBox - [Download](https://www.virtualbox.org/wiki/Linux_Downloads)
 * Check the following ports are available in your machine: 8080, 8220 and 8320.
 * Once you donwload the repo please be sure to remove any .vagrant folder in place to prevent any incompatibility with users or permissions.

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
 - Check vagrant is running:$ vagrant -v
 - Run the machine with the custom bootstrap:$ vagrant up --provision
 - Check the progress of the deployment with the internal log system:$ tail -f log-file.txt
 - Once the process is completed, you can get access to the site directly on your browser by typing: http://localhost:8220 for QA, 8320 for Production and 8080 for Jenkins.
```

### How it works

When the "vagrant up --provision" runs, it calls to the bootstrap script to run the following steps in the order:

 * Update the local system.
 * Install Docker CE
 * Install Docker Compose
 * Build the custom images for the containers.
 * Deploy the new stack with Docker Compose.

### Depends on

This workshop depends on the App's report that can be found [here](https://github.com/sergioandresmeneses/DevOps-Workshop-App).


#### And about the Container?

The stack runs with three containers: datacontainer, jenkins and nginxservice:

 * Datacontainer is a data-storage container for the files used by Jenkins.
 * Jenkins is the service itself.
 * app-qa and app-prod are the containers for the app.


## Running the tests

You can test the deployment of the infra with the log-file.txt directly:
```
$ tail -f log-file.txt
```

## Built With

* [VagrantBox bionic64](https://app.vagrantup.com/ubuntu/boxes/bionic64)
* [Docker](https://docs.docker.com/)
* [Docker-Compose](https://docs.docker.com/compose/) 
* [Jenkins-Image](https://hub.docker.com/_/jenkins)
* [Nginx Image for Docker](https://hub.docker.com/_/nginx)


## Authors

* **Sergio Meneses** - *Sysadmin Senior - CloudOps -  Globant* - [contact](mailto:sergio.meneses@globant.com).
* **Gabriel Diaz** - *DevOps Senior - CloudOps - Globant* - [contact](mailto:gabrielfelipe.diaz@globant.com).
