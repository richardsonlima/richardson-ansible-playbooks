# richardson-ansible-playbooks
richardson-ansible-playbooks

```
ansible-playbook -i inventory/hosts.ini i --private-key="~/.ssh/id_rsa" --become -e ansible_user=ubuntu  --extra-vars "ansible_sudo_pass=SUDO-PASSWORD" playbooks/playbook.yml -l machine-group 
