# Configure LAMP stack using Ansible Playbook.
---
1. Create inventory.ini (dynamic inventory)
2. playbook - lamp.yml
3. created roles for apache, mysql, php.

```yaml
lamp-playbook/
├── inventory.ini
├── lamp.yml
└── roles/
    ├── apache/
    │   └── tasks/main.yml
    ├── mysql/
    │   └── tasks/main.yml
    └── php/
        └── tasks/main.yml
```
