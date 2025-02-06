# Ansible Project: Automated Server Setup with Nginx 🚀

## Project Overview
This project automates the setup and configuration of a web server using Ansible. It streamlines the process of installing essential utilities, deploying Nginx, and ensuring secure SSH configuration on remote servers.

## Features ✨
- 🔄 Automated Server Configuration
- 🌐 Nginx Installation & Configuration
- 🛠️ Basic Utility Installation (curl, vim, git)
- 🔑 SSH Key Management
- 📦 Fully Automated Deployment

## Project Structure 📁
```
ansible-project/
├── inventory.ini        # Defines target servers
├── setup.yml           # Main Ansible playbook
├── roles/              # Role-based structure
│   ├── base/          # Installs basic utilities
│   ├── nginx/         # Installs and configures Nginx
│   ├── app/           # (Placeholder) Deploys an application
│   └── ssh/           # Manages SSH keys and security
```

## Prerequisites 📋
- Ansible installed via pipx (since Homebrew is unavailable on macOS 12)
- Remote Linux server (Ubuntu 24.10 tested)
- SSH access to the server

## Installation 💻

1. Install Ansible:
```bash
pipx install ansible
pipx ensurepath
```

2. Verify installation:
```bash
ansible --version
```

## Usage 🔧

### 1. Define Your Inventory
Create an `inventory.ini` file with your server details:
```ini
[webserver]
64.23.148.88 ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3

```

### 2. Run the Playbook
Execute the following command:
```bash
ansible-playbook -i inventory.ini setup.yml
```

### 3. Verify Deployment ✅

Check if Nginx is running:
```bash
systemctl status nginx
```

Expected output:
```
Active: active (running)
```

Test web server by visiting:
```
http://64.23.148.88
```
You should see the default Nginx welcome page.

## Troubleshooting 🔍

### Common Issues & Fixes

1. SSH Permission Issues:
```bash
chmod 600 ~/.ssh/id_rsa
ssh -i ~/.ssh/id_rsa your-user@64.23.148.88
```

2. Missing Role:
```bash
ansible-galaxy install geerlingguy.nginx
```

## Implemented Features ✅
* App deployment role successfully implemented
* SSL setup automated with Let's Encrypt
* Multi-server deployment configuration completed
Current Features 🌟
* 🔄 Automated Server Configuration
* 🌐 Nginx Installation & Configuration
* 🛠️ Basic Utility Installation (curl, vim, git)
* 🔑 SSH Key Management
* 📦 Full Application Deployment
* 🔒 Automated SSL Configuration
* 🖥️ Multi-Server Support
* 🚀 Zero-Downtime Deploymen

## Contributing 🤝
Contributions are welcome! Please feel free to submit a Pull Request.

## License 📄
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author ✍️
Eniayo Adediran

## Acknowledgments 🙏
- Ansible Community
- Contributors and maintainers
