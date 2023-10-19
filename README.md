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