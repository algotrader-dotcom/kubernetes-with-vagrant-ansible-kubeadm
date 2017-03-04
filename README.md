# kubernetes-vagrant-ansible
Install Kubernetes on Vagrant using Ansible.

## Requirements

- Vagrant
- Virtualbox
- Ansible

## Steps

First, create the machines.

```
vagrant up
```

Then, provision the machines.

```
ansible-playbook playbook.yml -i inventory -e @vars.yml
```


## Install UI Dashboard and UP

First SSH to Master, pls follow below guide:

Try to access via the NodePort and it is ok for v1.4.4

$ kubectl describe services kubernetes-dashboard -n kube-system
Name:           kubernetes-dashboard
Namespace:      kube-system
Labels:         app=kubernetes-dashboard
Selector:       app=kubernetes-dashboard
Type:           NodePort
IP:         10.109.227.200
Port:           <unset> 80/TCP
NodePort:       <unset> 32619/TCP
Endpoints:      10.44.0.3:9090
Session Affinity:   None
browse from another host to url: http://k8s-master.local:32619

http://master-ip:32697