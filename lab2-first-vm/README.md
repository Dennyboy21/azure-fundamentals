# Lab 2 – First Virtual Machine

**Objective:** Deploy my first VM in Azure, configure networking, and apply security best practices.

---

## Steps Taken
1. Created a new Resource Group for the lab.
2. Built a **Windows 11 VM (B1s)** with username/password auth.
   - ![VM Deployment](artifacts/screenshots/vm-deployment.png)
3. Configured RDP access limited to my home IP.
4. Connected via Remote Desktop.
   - ![RDP Login](artifacts/screenshots/rdp-login.png)
5. Installed updates, baseline tools, and snapshots.
   - ![Windows Update](artifacts/screenshots/windows-update.png)

---

## Security & Best Practices
- Restricted inbound RDP (3389) to **my IP only**.
- Applied latest patches immediately.
- Snapshotted VM for rollback before experimentation.

---

## Lessons Learned
- Limiting RDP scope is critical in cloud security.
- VM snapshots save time if configs go wrong.
- Azure portal provides immediate cost & usage visibility.

---
