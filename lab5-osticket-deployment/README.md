**Objective:** Deploy a Windows 10 VM in Azure and install/configure the osTicket Help Desk system, including dependencies (IIS, PHP, MySQL). Practice application deployment, configuration management, and basic hardening.

---

## Part 1 – VM Setup
1. Created a **Windows 10 VM** in Azure:
   - Name: `osticket-vm`
   - Size: 4 vCPUs
   - Username: `labuser`
   - Password: `osTicketPassword1!`
2. Connected via Remote Desktop to `osticket-vm`.
3. Downloaded and unzipped **osTicket-Installation-Files.zip** to the Desktop.

📸 Screenshots:
<img width="1920" height="1080" alt="osticket-vm-creation" src="https://github.com/user-attachments/assets/042d609c-6466-4d06-a165-b6fcadf2a6a4" />

<img width="953" height="987" alt="Screenshot 2025-09-14 071758" src="https://github.com/user-attachments/assets/9063d633-77fc-4b4e-b8c7-0aaccbbe64d4" />


---

## Part 2 – Install Dependencies
1. Installed **IIS with CGI** enabled:  
   `World Wide Web Services → Application Development Features → [X] CGI`
2. From the installation folder:
   - Installed **PHP Manager for IIS**  
   - Installed **Rewrite Module**  
3. Created directory `C:\PHP`.  
   - Extracted **PHP 7.3.8** into `C:\PHP`.
4. Installed **VC_redist.x86.exe**.
5. Installed **MySQL 5.5.62** (Typical Setup).  
   - Configured Standard Setup → Root user `root/root`.

📸 Screenshots:
<img width="950" height="988" alt="Screenshot 2025-09-14 075041" src="https://github.com/user-attachments/assets/7a15c3ca-0b2d-46e0-8a47-0b2719bfc340" />
<img width="956" height="984" alt="Screenshot 2025-09-14 075548" src="https://github.com/user-attachments/assets/970e9d12-f748-4764-911b-342e9a052c9c" />
<img width="856" height="579" alt="Screenshot 2025-09-14 080042" src="https://github.com/user-attachments/assets/cb4e436c-f56f-474a-bae2-d0575de429f0" />

---

## Part 3 – Configure IIS & PHP
1. Opened **IIS as Administrator**.
2. Registered PHP in IIS (PHP Manager → `C:\PHP\php-cgi.exe`).
3. Restarted IIS services.
4. Installed **osTicket v1.15.8**:
   - Copied “upload” folder into `C:\inetpub\wwwroot\`
   - Renamed folder to `osTicket`.
5. Reloaded IIS → Navigated to `http://localhost/osTicket`.

📸 Screenshots:
<img width="770" height="731" alt="Screenshot 2025-09-14 080420" src="https://github.com/user-attachments/assets/a154977f-62e3-498a-b7cc-09edd7861452" />
<img width="1512" height="989" alt="Screenshot 2025-09-14 080758" src="https://github.com/user-attachments/assets/2451b753-b28e-4379-b69a-323b7640cc9c" />

---

## Part 4 – Enable Required Extensions
1. In IIS → PHP Manager → Enabled:
   - `php_imap.dll`
   - `php_intl.dll`
   - `php_opcache.dll`
2. Refreshed osTicket site and confirmed extensions active.

📸 Screenshots:
<img width="1075" height="857" alt="Screenshot 2025-09-14 081721" src="https://github.com/user-attachments/assets/4744ac90-e48b-44b3-95c4-cacd8d41c6d8" />

---

## Part 5 – Final Configurations
1. Renamed config file:  
   `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php` → `ost-config.php`.
2. Adjusted permissions:  
   - Disabled inheritance, removed all existing permissions.  
   - Granted **Everyone → Full Control** (temporary for setup).
3. Continued setup in browser:
   - Helpdesk name: `My Helpdesk`
   - Default email: `helpdesk@example.com`

📸 Screenshots:
<img width="1177" height="734" alt="Screenshot 2025-09-14 082636" src="https://github.com/user-attachments/assets/5c887f27-fadd-4199-ad7f-9c7bb2736c6c" />

---

## Part 6 – Database Setup
1. Installed **HeidiSQL**.
2. Connected with `root/root`.
3. Created new database: `osTicket`.
4. Completed browser setup:
   - Database: `osTicket`
   - Username: `root`
   - Password: `root`
5. Clicked **Install Now!**

📸 Screenshots:
<img width="1086" height="542" alt="Screenshot 2025-09-14 082847" src="https://github.com/user-attachments/assets/ddf34dbb-c95c-49f9-92be-b29d9555b375" />
<img width="1302" height="896" alt="Screenshot 2025-09-14 083458" src="https://github.com/user-attachments/assets/55b56dca-ff79-4795-9bc9-22f33963cbb3" />

---

## Part 7 – Post-Install & Cleanup
- Admin portal: `http://localhost/osTicket/scp/login.php`  
- End-user portal: `http://localhost/osTicket/`  
- Deleted `C:\inetpub\wwwroot\osTicket\setup`.  
- Set `ost-config.php` to **Read-only** for security.

---

## 🔐 Security Practices
- Restricted VM RDP access to home IP.  
- Removed dangerous permissions after installation.  
- Deleted setup files to prevent reconfiguration.  
- Set `ost-config.php` to read-only.

---

## 📚 Lessons Learned
- Deploying a web application on IIS requires enabling correct PHP extensions.  
- Database setup and permissions are critical for application security.  
- Azure VMs can be used to replicate **real enterprise IT apps** for practice.  
- osTicket is a valuable platform to demonstrate **help desk and ticketing system knowledge**.

---

## Related Labs
- [Lab 2 – First Virtual Machine](../lab2-first-vm/README.md)  
- [Lab 4 – Networking Traffic Analysis](../lab4-networking-traffic/README.md)  
