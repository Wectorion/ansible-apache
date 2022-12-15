# Install Apache in a docker container with Ansible

## Requirements

First, you need to install Ansible :

`sudo apt-get install ansible`

Install Docker on the remote host (client) :

`sudo apt-get install docker.io`


## Deploy your config

Modifify the file files/secrets/credentials.yml :

`vault_ansible_password: YourPassword`

Encrypt your file :

`ansible-vault encrypt files/secrets/credentials.yml`

Now you can use the playbook :

`ansible-playbook -i hosts.yml --ask-vault-pass deploy.yml `


## Use SSH authentication

Generate an ssh key with :

`ssh-keygen -t rsa`

Copy the public key on the remote host :

`ssh-copy-id YourUser@YourClientIPaddr`

