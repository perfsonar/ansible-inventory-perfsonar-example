# ansible-inventory-perfsonar-example
Example Ansible perfSONAR Deployment for Supercomputing 2019

How to use this repository:
1.  log on to an Ansible bastion host

```
ssh ansible@a22.ps.dev.internet2.edu
```

2.  Get the official perfSONAR Ansible playbook and bootstrap it

```
git clone https://github.com/perfsonar/ansible-playbook-perfsonar.git
cd ansible-playbook-perfsonar
ansible-galaxy install -r  requirements.yml --ignore-errors
```

3.  add this repository to the perfSONAR Ansible playbook

```
git clone https://github.com/perfsonar/ansible-inventory-perfsonar-example.git
```

4. Provision perfSONAR infrastructure.  Optionally use Ansible's 'ping' to
   test connectivity first.

```
ansible-playbook \
  -i ansible-inventory-perfsonar-example/ \
  perfsonar.yml
```

5. Provision local changes to perfSONAR infrastructure

```
ansible-playbook \
  -i ansible-inventory-perfsonar-example/ \
  ansible-inventory-perfsonar-example/playbooks/perfsonar.yml
```

---

** Some useful commands to troubleshoot the environment **

Use Ansible ping to verify connectivity to targets.

```
ansible \
  -i ansible-inventory-perfsonar-example/ \
  all -m ping
```

