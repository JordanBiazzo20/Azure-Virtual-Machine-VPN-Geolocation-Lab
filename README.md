# Azure-Virtual-Machine-VPN-Geolocation-Lab

# 🌍 Azure Virtual Machine + VPN Geolocation Lab Installation & Configuration

This project explores how public IP addresses change across geographic regions by provisioning virtual machines in Microsoft Azure and using ProtonVPN to simulate location changes. This lab emphasizes the relationship between infrastructure geography, VPNs, and public IP tracking.

---

## 🧠 What I Learned

- How to provision and manage Virtual Machines in Microsoft Azure  
- How geographic regions affect public IP addresses and content delivery  
- How VPNs function to mask location and simulate cross-border browsing  
- Basic cleanup of Azure resources using Resource Groups  
- How websites behave differently based on geolocation  

---

## 🧰 Tools and Technologies Used

| Component          | Technology/Platform                  |
|--------------------|--------------------------------------|
| Cloud Provider     | Microsoft Azure                      |
| OS                 | Windows 10                           |
| Remote Access      | Remote Desktop Protocol (RDP)        |
| VPN Service        | ProtonVPN (Free Tier)                |
| Browser Tool       | [whatismyipaddress.com](https://whatismyipaddress.com) |

---

## 🌐 Step-by-Step Walkthrough

---

### ✅ Step 1: Capture Your Local IP Address

Before deploying anything:

1. On **your personal machine**, open a browser and visit:  
   🔗 [https://whatismyipaddress.com](https://whatismyipaddress.com)  
2. Copy your **current public IP** into a text file.
3. Note the **ISP and country/region** associated with it.

📸 _Screenshot Placeholder — Local Machine IP_  
![Local IP](screenshots/local-ip.png)

---

### 🧱 Step 2: Create Azure Resources

1. Log into [Azure Portal](https://portal.azure.com)
2. Create a new **Resource Group**
3. Deploy a **Windows 10 Virtual Machine** in a **different region or country** than your current one (e.g., East Asia or UK South)
4. Use default settings for everything else, but make sure RDP is enabled.

---

### 🖥️ Step 3: Connect to the Virtual Machine

1. Connect to the VM using **Remote Desktop**  
2. Inside the VM, open a browser and visit:  
   🔗 [https://whatismyipaddress.com](https://whatismyipaddress.com)  
3. Take note of the new public IP, location, and ISP.
4. Save the info in a text file named `azure-vm-ip.txt`.

---

### 🔐 Step 4: VPN Simulation Inside the VM

1. On your **personal machine**, create a free ProtonVPN account:  
   🔗 [https://account.protonvpn.com/signup?plan=free](https://account.protonvpn.com/signup?plan=free)
2. Back inside your Azure VM:
   - Download the **ProtonVPN Windows client**
   - Log in with your ProtonVPN credentials
3. Connect to a VPN server in **another country** (e.g., Japan or Netherlands)
4. After connecting, refresh:  
   🔗 [https://whatismyipaddress.com](https://whatismyipaddress.com)  
5. Record the new IP, region, and ISP to a third text file: `vpn-ip.txt`

---

### 🌐 Step 5: Observe Region-Specific Web Behavior

With VPN still active inside the VM:

1. Visit the following websites and take note of any changes:
   - 🔍 [https://google.com](https://google.com)
   - 🛍️ [https://amazon.com](https://amazon.com)
   - 🎬 [https://disney.com](https://disney.com)
2. Note if:
   - The site loads in a different **language**
   - URLs redirect to regional domains (e.g., `.jp`, `.nl`)
   - Any content seems tailored to that country


---

### 🧹 Step 6: Clean Up Azure Resources

1. Go back to Azure Portal  
2. Locate the **Resource Group** you created  
3. Click **Delete Resource Group**  
4. Confirm that all associated resources (VM, disk, network, etc.) are removed


---

## 📊 Summary of IP Changes

| Step                         | Observed Location | Public IP       | ISP           |
|------------------------------|-------------------|------------------|----------------|
| Personal Machine             | (e.g.) USA        | `xxx.xxx.xxx.xxx`| Comcast       |
| Azure VM (UK Region)         | United Kingdom    | `yyy.yyy.yyy.yyy`| Microsoft     |
| VPN (Connected to Japan)     | Japan             | `zzz.zzz.zzz.zzz`| ProtonVPN     |

---

## 💡 Key Takeaways

- Public IPs are geographically tied to data centers and VPN exit nodes.
- VPNs allow users to simulate internet access from a different country.
- Cloud-hosted VMs provide isolated environments for testing networking scenarios.
- Websites often serve regional content based on the visitor's IP geolocation.
- Cleaning up resources is essential for cost management and security.

---
