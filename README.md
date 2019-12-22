![ansible](ansible-logo.png)

# Ansible - Deploy OpenVPN server on CentOS 7 (with Firewalld)
Current Ansible template create OpenVPN server on CentOS 7 with enabled Firewalld service and join clients

## Requires Ansible version >= 2.7

## This template works with Ansible roles:

First you must copy all directory `roles` to `/etc/ansible/roles/`

```bash
sudo cp -R roles/* /etc/ansible/roles/ 
```

Edit your ansible config file `/etc/ansible/ansible.cfg`
Make sure that the server option is not commented out and contains the correct path

```bash
/etc/ansible/roles
```

### Template expect, that OpenVPN server will be `localhost` and clients will added to hosts file `/etc/ansible/hosts` like this:

```bash
[clients]
192.168.1.101 ansible_ssh_user=root
```

## Create cluster
```bash
ansible-playbook server.yaml
```

## Add nodes
```bash
ansible-playbook client.yaml
```
