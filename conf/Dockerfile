# Version: 0.0.1
FROM ubuntu:14.04.1
MAINTAINER Wille Faler "wfaler@recursivity.com"

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN apt-add-repository ppa:ansible/ansible
RUN apt-get update
RUN apt-get install -y ansible
add inventory-file /etc/ansible/hosts
ADD provision.yml provision.yml
RUN ansible-playbook provision.yml -c local
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80
CMD ["nginx"]