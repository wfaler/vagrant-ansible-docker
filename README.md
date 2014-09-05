## Install
The following assumes you already have _vagrant_ and _ansible_ installed on your local machine.

On your local machine, run:

	vagrant up

The _Vagrantfile_ is configured to start a VM with 2GB of ram and will provision all the pre-requisites to run docker provisioned by Ansible locally on the VM.  
It will also copy the files in the _conf_ directory onto the Docker host VM that is created, so you can run Docker from there.

Get on to the vagrant VM by running:

	vagrant ssh

## Working with Docker on your Vagrant VM
Building the docker image given the Docker file and provision.yml Ansible script:

	sudo docker build .

After this, you'll get an image id, which you can use in the following command:

	sudo docker run -d -p 80 [image id] nginx -g "daemon off;"

This will start the image in a new Docker container in daemon mode (it will not die straight after starting nginx).

	sudo docker ps -l

..will list all your docker containers. Under the _PORTS_ heading you'll be able to see what port the exposed port 80 is exposed to on your Docker host. You should be able to access the nginx server from that port. There are ways to make the port mapping deterministic, however I haven't gotten that far yet..
