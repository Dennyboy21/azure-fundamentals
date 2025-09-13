# Lab 4 – Networking Traffic Analysis in Azure

**Objective:** Deploy Windows + Linux VMs in Azure, place them in the same virtual network, and observe traffic between them using Wireshark. Explore how firewall rules, ICMP, SSH, DHCP, DNS, and RDP traffic appear in packet captures.

---

## Part 1 – VM Setup
1. Created a new **Resource Group** in Azure.
2. Deployed a **Windows 10 VM** into this group, allowing Azure to create a new **VNet + Subnet**.
3. Deployed a **Linux (Ubuntu) VM** into the **same Resource Group and Virtual Network**.
   - Authentication type: Username/Password
   - Confirmed both VMs share the same VNet/Subnet.
4. Left both VMs running to continue into Part 2.

📸 Screenshots:
- ![Windows VM Creation](artifacts/screenshots/windows-vm-creation.png)
- ![Linux VM Creation](artifacts/screenshots/linux-vm-creation.png)
- ![Resource Group Overview](artifacts/screenshots/resource-group-overview.png)

---

## Part 2 – Observing ICMP Traffic
1. Connected to the Windows VM using **Remote Desktop**.
2. Installed **Wireshark** and started packet capture.
3. Filtered for ICMP traffic only.
4. From Windows VM → pinged Ubuntu VM (private IP).
   - Observed request/reply in Wireshark.
5. From Windows VM → pinged `google.com`.
   - Observed public ICMP traffic.

📸 Screenshots:
- ![Wireshark ICMP Ping Ubuntu](artifacts/screenshots/icmp-ubuntu.png)
- ![Wireshark ICMP Ping Google](artifacts/screenshots/icmp-google.png)

---

## Part 3 – Firewall (NSG) & Traffic Analysis

### ICMP Blocking
1. Initiated a **continuous ping** from Windows VM → Ubuntu VM.
2. Edited the **Ubuntu VM’s Network Security Group (NSG)**:
   - Disabled inbound ICMP.
3. Observed ping failures + dropped packets in Wireshark.
4. Re-enabled ICMP → ping recovered.

📸 Screenshots:
- ![NSG ICMP Block](artifacts/screenshots/nsg-icmp-block.png)
- ![Ping Failure](artifacts/screenshots/ping-failure.png)

---

### SSH Traffic
1. In Wireshark, filtered for SSH traffic.
2. From Windows VM, used PowerShell to SSH into Ubuntu VM:
   ```powershell
   ssh labuser@<private-IP>
