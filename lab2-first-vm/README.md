# Lab 2 – First Virtual Machine

**Objective:** Deploy my first VM in Azure, configure networking, and apply security best practices.

---

## Steps Taken
1. Created a new Resource Group for the lab.
2. Built a **Windows 11 VM (B1s)** with username/password auth.
   <img width="1920" height="1080" alt="Screenshot 2025-09-14 102059" src="https://github.com/user-attachments/assets/62a933ae-0150-4f73-9c8e-e6d9d00a843c" />
3. Configured RDP access limited to my home IP.
4. Connected via Remote Desktop.
   <img width="1920" height="1080" alt="Screenshot 2025-09-14 101241" src="https://github.com/user-attachments/assets/01a98ca4-ae54-4080-b244-52344bff7daa" />
5. Installed updates, baseline tools, and snapshots.
   <img width="1333" height="1009" alt="Screenshot 2025-09-14 111551" src="https://github.com/user-attachments/assets/cd314ee5-98e4-4df5-9fc7-a4fb0fd2ddd2" />
   


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
