# FROM ansible/centos7-ansible:stable
FROM ansible/ubuntu14.04-ansible:stable

ENV ROLE_DIR /ansible/gitbucket

RUN mkdir $ROLE_DIR -p
WORKDIR $ROLE_DIR

# Install dependent roles (Only use dependent roles)
RUN ansible-galaxy install -p ../ distkloc.gitbucket

# Specify ansible.cfg path with environment variable
ENV ANSIBLE_CONFIG $ROLE_DIR/tests/ansible.cfg

ADD . $ROLE_DIR

RUN ansible-playbook tests/playbook.yml -i tests/inventory


ENTRYPOINT ["java", "-jar", "/usr/share/gitbucket/lib/gitbucket.war"]
