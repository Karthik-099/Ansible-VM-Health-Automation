# Ansible-VM-Health-Automation
Automated monitoring of virtual machines using Ansible, with daily HTML reports for CPU, memory, disk, and network usage sent via email.

# VM Health Monitoring and Resource Reporting with Ansible

This project demonstrates a production-style workflow for monitoring multiple virtual machines (VMs) using **Ansible**.  
It collects key resource metrics from all configured VMs and sends professional HTML reports via email on a scheduled basis.

---

## Problem Statement

In many organizations:
- Monitoring multiple VMs manually is time-consuming
- Resource usage data (CPU, RAM, disk) is scattered and hard to collect
- Daily reports for managers or stakeholders are created manually
- There is no standardized way to collect, format, and deliver VM health reports

This project solves these problems by automating metric collection, report generation, and email delivery using Ansible.

---

## Solution Overview

- **Ansible** acts as the central orchestrator
- Automatically installs and configures necessary packages on all VMs
- Collects system metrics including CPU, memory, disk, and network usage
- Generates professional HTML reports
- Sends reports automatically via email at scheduled times
- Scalable to monitor any number of VMs

---

## Architecture

1. The Ansible master node triggers the playbooks.
2. Target VMs are configured and monitored.
3. Metrics (CPU, RAM, disk, network) are collected from all VMs.
4. HTML reports are generated using templates.
5. Reports are emailed to designated recipients.
6. Optional: Playbooks can be scheduled with cron for daily reporting.

        +-------------------+
        |   Ansible Master  |
        +-------------------+
                |
    -----------------------------
    |      |       |      |     |
   VM1    VM2     VM3    ...   VMn


---

## Tech Stack

- **Ansible** – automation and orchestration  
- **Python** – metrics collection and email delivery  
- **HTML** – report formatting  
- **Linux (Ubuntu)** – control and target machines  
- **SMTP** – email delivery  

---

## Repository Structure

```text
Ansible-VM-Health-Automation/
├── ansible.cfg            # Ansible configuration
├── inventory              # List of target VMs
├── group_vars/            # Variables for VM groups
├── playbook.yaml          # Main orchestration playbook
├── collect_metrics.yaml   # Collects VM metrics
├── send_report.yaml       # Generates and sends HTML reports
├── templates/             # HTML templates for reports
├── README.md              # Project documentation
└── .gitignore             # Ignored files
