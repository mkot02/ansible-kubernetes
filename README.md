# Ansible Role: kubernetes
Install and configure single control-plane kubernetes cluster.

## Requirements
Installed docker on all nodes

## Role Variables
A description of the settable variables for this role. 

### Mandatory variables

#### Group variables
Address of subnet for pod network:
```
k8s_pod_network_cidr: <subnet address>
```

#### Host variables
Node role in kubernetes cluster:
```
k8s_role: "master"
k8s_role: "worker"
```

### Default variables
Proxy settings (optional):
```
http_proxy: ''
https_proxy: ''
no_proxy: ''
```

Name of kubelet service (optional):
```
kubelet_service: kubelet.service
```

Flag indicating if pods can be created on master node (optional):
```
k8s_allow_pods_on_master: yes
```

URL to network addon for pod network - default is Flannel (optional)
```
k8s_addon_network_url: https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
```

## Dependencies
None

## Example Playbook
```
- hosts: kubernetes
  roles:
    - mkot02.docker
```

## License
MIT

## Author Information
Marcin Kotarba, 2019
