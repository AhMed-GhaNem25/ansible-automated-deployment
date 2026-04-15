# Simple Ansible Deployment Project

A simple Ansible project to automate the installation and deployment of a Node.js application on a remote server.

---

## Prerequisites

- A Linux-based control machine
- SSH access to the target server
- `ansible` installed (see below)

---

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Ahmed-Moourad/simple-nodejs-app
cd simple-nodejs-app
```

### 2. Install Ansible

```bash
apt update
apt install ansible
```

> **Note:** If you encounter errors during installation, use pip instead:
> ```bash
> pip install ansible
> ```

### 3. Configure the Hosts File

Edit the `hosts` file and add your server's IP address and SSH key information:

```ini
[your-server-group]
YOUR_SERVER_IP ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem
```

### 4. Configure the Playbook

Edit `deploy-nodejs.yaml` and update the following:
- Replace `your-server-ip` with your actual server IP or inventory group name
- Update `yourpath` references with the correct absolute paths on your machine
- Ensure `Vars.yaml` exists at the specified path with the correct variables

### 5. Run the Playbook

```bash
sudo ansible-playbook -i hosts deploy-nodejs.yaml
```

---

## Project Structure

```
.
├── hosts               # Inventory file (server IPs & SSH config)
├── deploy-nodejs.yaml  # Main Ansible playbook
└── Vars.yaml           # Variables file (app_file, dest_path, etc.)
```

---

## Additional Resources

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/)
- [Ansible GitHub Repository](https://github.com/ansible/ansible)

---

Happy automating! 🚀
