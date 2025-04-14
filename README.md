# Linux RHEL Server Setup

## Overview
This project provides an automated approach to configuring, managing, and monitoring network and system settings on multiple Linux servers using Ansible. The playbook ensures consistency, reliability, and ease of management across different environments.

## Features
- **Network Configuration** – Automate setup of network interfaces, IP addressing, and routing.
- **User Management** – Create and manage user accounts with defined permissions.
- **Package Management** – Install and update required packages using package managers.
- **System Tuning** – Optimize system-level parameters for better performance.
- **Monitoring** – Deploy Prometheus, Grafana, and SNMP for comprehensive monitoring.
- **Security** – Configure SELinux, firewall (firewalld/iptables), and enhance system hardening.
- **Time Synchronization** – Configure Chrony for accurate timekeeping across servers.
- **Server Partitioning** – Automate disk partitioning and mounting.
- **System Updates** – Perform Yum updates to keep systems secure and current.
- **Configuration Scan** – Generate detailed scan reports of system configurations.

## Prerequisites
- **Ansible Installed** – Ensure Ansible is installed on the control node.
- **SSH Access** – Control node must have SSH access to all target nodes.
- **Sudo Privileges** – The Ansible user must have sudo access on the target machines.

## Project Structure
```sh
linux-rhel-server-setup/
│── ansible.cfg
│── inventory/
│   ├── dev.ini
│── playbooks/
│   ├── site.yml
│── roles/
│   ├── connectivity-test/
│   ├── network-configuration-set/
│   ├── user-management/
│   ├── package-management/
│   ├── system-tuning/
│   ├── monitoring/
│   ├── server-partitioning/
│   ├── grafana/
│   ├── node_exporter/
│   ├── prometheus_installation/
│   ├── snmp_notifier/
│   ├── chrony_config/
│   ├── selinux-configuration/
│   ├── systemctl_runlevel/
│   ├── yum_update_and_sync/
│   ├── scan/
```

## Installation
Clone the repository:
```sh
git clone https://github.com/thanurarukshan/Linux_RHEL_Server_Setup.git
```

Navigate into the project directory:
```sh
cd linux-rhel-server-setup
```

Install Ansible:
```sh
# For Debian-based systems
sudo apt update && sudo apt install ansible -y

# For RHEL/CentOS-based systems
sudo yum install ansible -y
```

## Usage
1. Edit the `inventory/dev.ini` file to include your target servers.
2. Run the playbook:
```sh
ansible-playbook -i playbooks/dev.ini playbooks/site.yml --ask-become-pass
```
3. Monitor playbook execution and review output or logs for any errors.

## Role Descriptions
- **connectivity-test** – Verifies server reachability before execution.
- **network-configuration-set** – Applies IP settings, routes, and network interfaces.
- **user-management** – Automates user and group account creation.
- **package-management** – Installs OS-level dependencies and packages.
- **system-tuning** – Adjusts kernel and sysctl settings.
- **monitoring** – Installs Prometheus, Grafana, Node Exporter, and SNMP agents.
- **server-partitioning** – Automates disk partitioning using `fdisk` or `parted`.
- **security** – Configures SELinux, firewalls, and secures open ports.
- **time-sync** – Installs and configures Chrony for NTP synchronization.
- **scan** – Collects and saves detailed config reports (`scan_reports/`) with metadata.

## Contribution
We welcome contributions from the community! To contribute:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature-name`)
3. Commit your changes
4. Push to your fork
5. Submit a pull request

Report issues or suggest enhancements through the GitHub Issues page.

## Contact
������ For queries or contributions, email: thanurarukshan2000@gmail.com


