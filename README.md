# Ansible LAMP Stack Playbook

- This project automates the deployment of a full LAMP Stack (Linux, Apache, MySQL, PHP) using Ansible Roles. It is designed to be modular, allowing each component of the web stack to be managed independently.

## 🏗 Project Structure
```yaml
text
lamp-playbook/
├── inventory.ini      # Defines target hosts and connection details
├── lamp.yml           # Main entry-point playbook
└── roles/             # Modular service configurations
    ├── apache/        # Installs and configures Apache HTTP Server
    │   └── tasks/
    │       └── main.yml
    ├── mysql/         # Installs and secures MySQL Database
    │   └── tasks/
    │       └── main.yml
    └── php/           # Installs PHP and necessary modules
        └── tasks/
            └── main.yml
```

## 🚀 Getting Started

### Prerequisites
- Ansible installed on your control node.
- Target nodes with SSH access and sudo privileges.
- Connectivity defined in inventory.ini.

***Usage***

- Configure Inventory: Update inventory.ini with your server's IP address or hostname.
```yaml
ini
[webservers]
your_server_ip ansible_user=your_ssh_user ansible_ssh_private_key_file=~/path_to/.ssh/ssh_key.pem
```


- Run Playbook: Execute the deployment using the following command:
```bash
ansible-playbook -i inventory.ini lamp.yml --become
```

**The --become flag ensures tasks run with root privileges.*

***🛠 Role Descriptions ***

#### Role: 	   Responsibility

- Apache: 	Installs apache2, ensures the service is running, and opens firewall ports if necessary.

- MySQL:	Installs mysql-server, manages the database service, and creates initial databases/users.

- PHP:	Installs the PHP interpreter and the libapache2-mod-php module for web server integration.

##### 🧪 Verification
- Once the playbook completes, you can verify the installation by visiting your server's IP in a browser: