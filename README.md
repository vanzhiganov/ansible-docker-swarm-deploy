# ansible-docker-swarm-deploy

## Example

**Inventory**

Scenario: one manager multiple nodes

```
server1 ansible_host=192.168.10.100 ansible_user=root ansible_python_interpreter=python3
server2 ansible_host=192.168.10.101 ansible_user=root ansible_python_interpreter=python3
server3 ansible_host=192.168.10.102 ansible_user=root ansible_python_interpreter=python3

[swarm_manager]
server1

[swarm_nodes]
server1
server2
server3
```

**Deploy**

```shell
ansible-playbook -i inventory.ini playbook-00-prepare.yml
ansible-playbook -i inventory.ini playbook-01-init.yml
```
