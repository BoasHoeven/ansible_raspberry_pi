# A simple Flask app container.
FROM geerlingguy/docker-ubuntu2004-ansible
MAINTAINER Jeff Geerling <geerlingguy@mac.com>

# Install Flask app dependencies.
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3-pip
RUN apt-get install -y wget
RUN apt-get install -y curl
RUN apt-get install -y ffmpeg
RUN pip3 install flask

# Install playbook and run it.
COPY playbook.yml /etc/ansible/playbook.yml
COPY api.py.j2 /etc/ansible/api.py.j2
RUN mkdir -m 755 /opt/www
RUN ansible-playbook /etc/ansible/playbook.yml --connection=local

EXPOSE 5000