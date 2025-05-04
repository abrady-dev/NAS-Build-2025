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
