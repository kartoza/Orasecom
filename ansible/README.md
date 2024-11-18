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
