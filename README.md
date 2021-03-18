# Prerequisites

```
sudo dnf -y install ansible
ansible-galaxy collection install community.kubernetes
```

# Usage
1. cp `config.yml.example config.yml`
1. Update `src_kubeconfig` and `dst_kubeconfig` in `config.yml` with the paths to the kube config for each cluster
1. Edit other options as desired in `config.yml`
1. Add transform tasks to transforms.d as desired. A couple simple examples are included.
1. Run `ansible-playbook migrate.yml -e namespace=robot-shop`

# Issues
- Not all APIs are found as expected: https://github.com/ansible-collections/community.kubernetes/issues/380
