# richardson-ansible-playbooks
richardson-ansible-playbooks

```
ansible-playbook -i inventory/hosts.ini i --private-key="~/.ssh/id_rsa" --become -e ansible_user=ubuntu  --extra-vars "ansible_sudo_pass=SUDO-PASSWORD" playbooks/playbook.yml -l machine-group 
```

## Examples

```yaml
- hosts: all
  vars:
    app_users:
      - { db_name: "", user: "", pwd: "", roles: ["readWrite", "userAdmin"] }

  roles:
    - { role: mongodb, flags: ['install'] }
    - { role: mongodb, flags: ['save-config'] }
    - { role: mongodb, flags: ['reset-storage'] }
    - { role: mongodb, flags: ['init-replica-set'] }
    - { role: mongodb, flags: ['add-replica-set'] }
    - { role: mongodb, flags: ['db_create'] }
```

```bash
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['install']}"
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['save-config']}"
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['reset-storage']}"
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['init-replica-set']}"
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['add-replica-set']}"
ansible-playbook playbooks/mongodb.yml -e "{'flags': ['db_create']}"
```
