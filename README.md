# CapRover-playbook

pip install ansible --user

## Create ssh key
```console
ssh-keygen -t rsa
ssh-copy-id -i ~/.ssh/id_rsa.pub ip_machine
ssh-agent bash
ssh-add ~/.ssh/id_rsa
```
## Set your variables
Rename files and change values.
```console
mv inventory_copy.ini inventory.ini
mv ubuntu-22.04.03/group_vars/caprover_copy.yml ubuntu-22.04.03/group_vars/caprover.yml
```

## Execute the playbook
```console
ansible-playbook -i inventory.ini  ubuntu-22.04.03/playbook.yml -K
```

## Setup DNS on Ansible main node (wildcard)
https://askubuntu.com/a/1031896

## Install CapRover Cli
```console
 npm install -g caprover
```

Connect to CapRover machine using: `caprover login`

## Deploy your app
Create an app on CapRover dashboard and run this command from your app directory (captain-definition file)
```console
caprover deploy
```