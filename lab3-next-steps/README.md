# Lab 3 – Next Steps in Azure

**Objective:** Plan and prepare for more advanced Azure labs that expand beyond resource basics and VMs. This stage focuses on monitoring, segmentation, and security hardening.

---

## Planned Labs

### 1) Azure Monitor & Log Analytics
- Enable **Azure Monitor** on existing resources.
- Collect logs from VM and storage account.
- Create sample queries in Log Analytics Workspace.
- Export logs for use in a SIEM (Splunk/ELK/Wazuh).
- ![Azure Monitor Setup](artifacts/screenshots/azure-monitor.png)

---

### 2) Network Security Groups (NSGs)
- Create an NSG and apply it to a subnet and VM NIC.
- Configure inbound/outbound rules (allow RDP from home IP, deny all else).
- Test connectivity before and after rules.
- Document the effect of NSG rules.
- ![NSG Rules](artifacts/screenshots/nsg-rules.png)

---

### 3) Linux VM Deployment
- Deploy a Linux VM (Ubuntu LTS).
- Configure SSH access restricted to home IP.
- Install basic tools: fail2ban, ufw firewall.
- Run updates and practice secure baseline setup.
- ![Linux VM Deployment](artifacts/screenshots/linux-vm.png)

---

### 4) Cost Management Refinement
- Set up Azure cost alerts.
- Tag resources for cost tracking.
- Simulate lab cleanup and verify updated cost analysis.
- ![Cost Alerts](artifacts/screenshots/cost-alerts.png)

---

## Security Practices to Reinforce
- Always scope access (RDP/SSH) to trusted IPs only.
- Patch systems immediately upon deployment.
- Use NSGs and firewalls as layered defenses.
- Monitor logs continuously, export for long-term analysis.

---

## Lessons I Expect to Learn
- How Azure logs map into a SOC workflow.
- Practical experience with cloud firewalls (NSGs).
- Administering Linux in a cloud environment.
- Cost awareness when scaling beyond free tier.

---

## Related Labs
- [Lab 1 – Resource Group & Storage Account](../lab1-resource-group-storage/README.md)
- [Lab 2 – First Virtual Machine](../lab2-first-vm/README.md)

---
