## Deploy Zabbix with Ansible

First, edit the following file:

```
nano zabbix_install.yml
```

You need to edit the following values according to you:

```
database_name: "zabbix"
database_username: "zabbix"
database_password: "7c642U7frI5KppwSnD3"
nginx_listen_port: "80"
nginx_server_name_or_ip: "10.10.10.100"
```

Then define your server in the following file:

```
nano /etc/ansible/hosts
```

Now deploy the configuration:

```
ansible-playbook main.yml
```

After successfully deploying Zabbix, complete the remaining installation by logging in from the link below:

```
http://your-ip:80
```
