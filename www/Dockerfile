# Install Flask app dependencies.
RUN apt-get update
RUN apt-get install -y python3-pip
RUN pip3 install flask

# Install playbook and run it.
COPY playbook.yml /etc/ansible/playbook.yml
COPY api.py.j2 /etc/ansible/api.py.j2
RUN mkdir -m 755 /opt/www
RUN ansible-playbook /etc/ansible/playbook.yml --connection=local

EXPOSE 5000