# Ansbile raw

```
ansible all -m ping

ansible -i hosts mac --list-hosts
ansible -i hosts all -m raw -a 'echo "Hello GVR"'
ansible -i hosts mac -m ping
```

# Run playbooks

```
ansible-playbook playbook1-ping.yml --check --ask-pass

ansible-playbook playbook1-ping.yml --check
ansible-playbook playbook2-ghost.yml --check
ansible-playbook playbook3-mongo.yml --check
ansible-playbook playbook4-ubuntu.yml --check
```

# Create Ansible Roles

```
mkdir roles
cd roles
ansible-galaxy init role1
ansible-galaxy init role2
```

# Call main playbook using roles

```
ansible-playbook main.yaml --check
```

# Call playbooks directly

```
ansible-playbook ./playbooks/playbook1-ping.yml --check
ansible-playbook ./playbooks/playbook2-ghost.yml --check
ansible-playbook ./playbooks/playbook3-mongo.yml --check
ansible-playbook ./playbooks/playbook4-ubuntu.yml --check
```

# Add User with sudo access

- adduser tstuser1 & enter password
- cut -d: -f /etc/passwd
- su tstuser1
- cd ~
- sudo vi /etc/ssh/sshd_config
- AllowUsers tstuser1 root
- systemctl restart sshd (service restart sshd)

# sudo accesss to user

usermod -aG sudo tstuser1
