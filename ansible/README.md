# Ansible Deployment Guide

This repository contains Ansible playbooks and configurations to manage and deploy services.

## Prerequisites

Before running the Ansible script, ensure the following prerequisites are met:

1. **Ansible Installed:**
   - Install Ansible on your local machine:
     ```bash
     sudo apt update
     sudo apt install ansible -y
     ```
   - Verify installation:
     ```bash
     ansible --version
     ```

2. **Inventory File:**
   - Ensure the inventory file (`prd.inv`) exists at:
     ```
     inventories/ktz/prd/prd.inv
     ```

3. **SSH Access:**
   - Ensure you have SSH access to the target servers defined in the inventory.
   - Add your SSH key if necessary:
     ```bash
     ssh-copy-id user@server-ip
     ```

---

## How to Run the Ansible Playbook

To execute the playbook for production, use the following command:

```bash
ansible-playbook -i inventories/ktz/prd/prd.inv playbook.yml
```

## Using Tags
Tags allow you to selectively run specific tasks or roles within the playbook.

### Deploy Application

Use the deploy tag to focus on tasks related to application deployment, such as building Docker images and starting services:

```bash
ansible-playbook -i inventories/ktz/prd/prd.inv playbook.yml --tags "deploy"
```

### Update Repository

Use the repo tag to update the repository to the latest main branch:

```bash
ansible-playbook -i inventories/ktz/prd/prd.inv playbook.yml --tags "repo"
```

### Skip Specific Tags

If you want to skip certain operations, such as repository updates, use the --skip-tags option:

```bash
ansible-playbook -i inventories/ktz/prd/prd.inv playbook.yml --skip-tags "repo"
```
