# Prerequisites

```
sudo dnf -y install ansible
ansible-galaxy collection install community.kubernetes
```

# Usage
The source playbook will quiesce the application in order to ensure data integrity. At the moment this means scaling down deployments, but should be expanded to scale down other scalable resources (deploymentconfigs, ...), delete standalone pods, etc.

Source cluster:  
`ansible-playbook backup.yml -e namespace=robot-shop`

Destination cluster:  
`ansible-playbook restore.yml -e namespace=robot-shop`
