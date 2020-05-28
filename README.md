# Kurbernetes Cluster Laboratory

Traning Uncomplicating Ansible

## Usage

1 - Open Terminal on Directory 01_provisioning and execute:
```
ansible-playbook -i hosts main.yml
```

2 - Open 'hosts' file and identify the private and public IPs that you want as master and slaves on cluster.

Note: Don't forget to add the EC2 access key to the ssh agent of the machine that is going to run ansible.

3 - Edit the hosts file in the '02_install_k8s' folder with the public IPs for master and slaves and the private IP for 'K8S_MASTER_NODE_IP' environment variable.

```
[k8s-master]
# public master ip bellow

[k8s-workers]
# public slaves ips bellow

[k8s-workers:vars]
K8S_MASTER_NODE_IP=[private master ip here, without brackets] 
K8S_API_SECURE_PORT=6443
```

4 - Open Terminal on Directory '02_install_k8s' and execute:
```
ansible-playbook -i hosts main.yml
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


## License
[MIT](https://choosealicense.com/licenses/mit/)
