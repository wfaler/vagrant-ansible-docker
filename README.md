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

	sudo docker run -d -p 80:80 -v /home/vagrant/html:/usr/share/nginx/html [image id]


This will start the image in a new Docker container in daemon mode (it will not die straight after starting nginx), with the container port 80 mapped to the hosts port 80.
Further more, it will mount the /home/vagrant/html directory on the host as the nginx html directory on the container.

