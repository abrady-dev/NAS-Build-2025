# Tailscale + TrueNAS SMB Remote Access Setup

This document outlines how I configured remote access to my TrueNAS SMB share using Tailscale. This allows me to connect to my NAS from anywhere while traveling using Tailscale's VPN.

---

## 🔧 Setup Summary

* **Platform**: TrueNAS SCALE
* **Access method**: SMB (macOS Finder via `smb:// and windows File Exploror`)
* **VPN**: Tailscale
---

## 🪜 Step-by-Step Setup Guide

### 1. Install and Configure Tailscale on TrueNAS

* Navigate to **System Settings > Services > Tailscale** in TrueNAS.
* Enable the service.
* Proceed to the TailScale website and generate a new Auth Key. This is used to verify the link between the vpn and my server.
* Copy the new Auth key in the respective field 
* I chose to skip everything from Log, Spare, Cache, MetaData, and Dedup because at this current moment, I have no use for them and I do not know enough about them; as such, further review is needed on the uses of these.
* Review and then Install. 
* Authenticate using your Tailscale account.
* Ensure the TrueNAS host appears in your Tailscale admin panel with a 100.x.x.x IP.

### 2. Enable MagicDNS (Optional)

* In the Tailscale admin panel ([https://tailscale.com/admin](https://tailscale.com/admin)), go to **DNS settings**.
* Enable MagicDNS.
* This lets you refer to machines by name instead of IPs (e.g. `truenas` instead of `100.94.167.95`).

### 3. Disable Local LAN Access (To Force Tailscale Usage)

* Go to the Tailscale admin panel.
* Find your **TrueNAS node**.
* Under **ACLs or machine settings**, disable "Allow local LAN access".
* This ensures the machine is only accessible via Tailscale, even when you're home.

### 4. Set Up SMB on TrueNAS

* Go to **Shares > Windows (SMB) Shares** in the TrueNAS web UI.
* Ensure an SMB share is created and pointing to your data directory.
* Set the correct permissions for the user you'll authenticate as.
* Bind the SMB service to **both** your local IP (e.g. `192.168.1.217`) and the Tailscale IP **(manually add 100.x.x.x if needed).**

### 5. Connect from macOS

* Open Finder > Go > Connect to Server.
* Use: `smb://100.x.x.x` (your Tailscale IP for TrueNAS)
* Save both local (`192.168.1.217`) and Tailscale (`100.x.x.x`) addresses as favorites.
* When Tailscale is active, use the `100.x.x.x` to connect.

### 6. Testing Remote Access

* Disconnect from your home network (use a phone hotspot).
* Enable Tailscale on your Mac.
* Use the saved `smb://100.x.x.x` connection.
* Confirm you can browse and access the NAS remotely.

---

## 🧪 Issues Encountered & Fixes

### "There was a problem connecting to the server..."

* **Cause**: Tailscale not connected / IP mismatch / SMB not bound to 100.x.x.x
* **Fixes**:

  * Ensure Tailscale is active.
  * Bind SMB service to the Tailscale IP in TrueNAS.
  * Check IP in Tailscale admin and match it in Finder.
---

## 💡 Notes

* Tailscale IPs (100.x.x.x) work across all networks as long as Tailscale is active.
* LAN IP (192.168.x.x) will only work when on the same Wi-Fi/subnet.
* Saving both IPs in Finder lets you connect depending on whether you're home or remote.
* You can set Tailscale to auto-start on boot for headless NAS convenience.

---

## 🧾 To Do / Future Enhancements

* [ ] Test MagicDNS access from outside (e.g. `smb://truenas`)
* [ ] Create Tailscale ACLs for limited access to NAS only
* [ ] Add screenshots and diagrams for GitHub readme visual clarity
* [ ] Possibly add Tailscale to other home devices (for mesh access)

---	
