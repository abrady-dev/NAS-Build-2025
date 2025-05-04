# Portainer Setup on TrueNAS SCALE

This document outlines the setup process for installing and configuring Portainer in a TrueNAS SCALE environment, using a dedicated dataset and persistent storage configuration.

---

## 📁 Dataset Preparation

1. **Created a dedicated dataset for Portainer**
   - Dataset Name: `portainer`
   - Location: Under the main pool (`bananiserver/portainer`)
   - Preset: Default (can optionally use "Apps" if it helps for clarity)
   - Purpose: Isolate Portainer's data from other apps for easier backups and troubleshooting.

---

## ⚙️ Application Configuration (Portainer via TrueNAS SCALE GUI)

1. **Navigate to:** `Apps` > `Available Applications` > **Search for "Portainer"**

2. **Click "Install"** and fill out the form:
   - **Application Name**: `portainer`
   - **Version**: (use latest stable unless specific version required)

### Storage Configuration:

- **Use an existing dataset for persistent data**
  - Selected: `bananiserver/portainer`
  - This ensures that Portainer's settings and state survive restarts or upgrades.

- No need to manually create additional sub-datasets like `data` unless you plan to manage large volumes or want separate datasets per container volume.

---

## 🖥️ Web Interface Access

After deployment:

- Access Portainer via:

- (Check the assigned port in the Portainer app summary after install)
- Log in and create the initial admin account.

---

## ✅ Verifying Setup

- Ensure the container status is **Running** in the **Installed Applications** tab.
- Navigate to the web interface and confirm dashboard loads successfully.
- (Optional) Enable TLS if running over public networks or through Tailscale.

---

## 📁 Notes on Clean App Management

- Creating **individual datasets per app** is a clean and scalable strategy.
- This allows for:
- Better permission control
- More efficient snapshotting
- Easy backups/restores

---

## 💡 Optional Improvements

- Use **Tailscale** to securely access Portainer remotely.
- Set up automatic updates through the TrueNAS App catalog.
- Monitor logs through the **App > Manage > Logs** section.

---

