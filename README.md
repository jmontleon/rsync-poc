# Prerequisites

```
sudo dnf -y install ansible
ansible-galaxy collection install community.kubernetes
```

# Usage
The source playbook will quiesce the application in order to ensure data integrity. At the moment this means scaling down deployments, but should be expanded to scale down other scalable resources (deploymentconfigs, ...), delete standalone pods, etc.

Source cluster:
- `ansible-playbook backup.yml -e namespace=robot-shop`

Transform:
- Add task files to transform resources as desired in the `transform.d` directory
- `ansible-playbook transform.yml -e namespace=robot-shop`

Destination cluster:
- `ansible-playbook restore.yml -e namespace=robot-shop`

# Issues
- Not all APIs are found as expected: https://github.com/ansible-collections/community.kubernetes/issues/380
