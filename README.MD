# Instructions
1. `ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa`
2. Copy `~/.ssh/id_rsa.pub` and paste at end of `~/.ssh/authorized_keys` at remote machine
3. in inventory provide password or make user sudo any command without password - `username ALL=(ALL) NOPASSWD: ALL`

Sample `inventory.ini`
```ini
your_remote_host ansible_host=<ip> ansible_user=<user> ansible_ssh_private_key_file=~/.ssh/id_rsa
```

```bash
# To check host
ansible remote_servers -m ping

# To run a playbook
ansible-playbook -i inventory.ini playbook.yaml
```
