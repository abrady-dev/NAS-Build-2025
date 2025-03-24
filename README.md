# Home NAS Build – 2025

Hello my name is Aden and this is documentation for my first project a small home NAS build! This build was designed as a quiet, energy-efficient, and capable home NAS for personal file storage, backups, and future exploration using VM's. Below you'll find the complete parts list, cooling setup, configuration plans, and photos of the build.

---

## 🧰 Parts List

| Component       | Model |
|----------------|-------|
| **CPU**        | AMD Ryzen 5 5600G 3.9 GHz 6-Core Processor |
| **CPU Cooler** | Thermalright Assassin X 120 Refined SE (66.17 CFM) |
| **Motherboard**| Gigabyte B550M AORUS Elite AX (Micro ATX, AM4) |
| **Memory**     | TEAMGROUP T-Force Vulcan Z 32GB (2 x 16GB) DDR4-3200 CL16 |
| **Boot Drive** | Patriot P300 256GB M.2 PCIe 3.0 x4 NVMe SSD |
| **Storage Drives** | 2x Seagate IronWolf NAS 4TB 5400 RPM 3.5" HDD |
| **Case**       | Cooler Master N400 ATX Mid Tower |
| **Power Supply** | Thermaltake Toughpower GX2 600W 80+ Gold |
| **Case Fan**   | Noctua NF-P12 redux-1700 PWM (70.75 CFM, 120mm) + Stock Case Fans |

---

## 🌀 Cooling Configuration

| Fan Location | Fan | Direction |
|--------------|-----|-----------|
| Front (stock) | 120mm | Intake |
| Rear (stock)  | 120mm | Exhaust |
| Top (added)   | Noctua P12 Redux | Exhaust |
| Side (future) | TBD (optional) | Intake over HDDs |

The case provides strong airflow potential, with the Noctua P12 added for enhanced top exhaust and quieter performance. Planning to add a side intake in the future to help cool the hard drives directly. I might change the fan configuration to having the Noctua Fan at the Fan as well (TBD)

---

## 💾 Storage Layout

- **Boot**: Patriot P300 NVMe SSD (for TrueNAS or future OS)
- **Data**: 2x 4TB Seagate IronWolf NAS drives (mirrored or ZFS RAIDZ planned)
- Future expansion will use remaining SATA ports, or add a PCIe SATA controller if needed.

---

## 🖥️ Planned Software & Setup

- **OS**: TrueNAS SCALE (Linux-based, great for ZFS and containers)
- **Services**:
  - File sharing via SMB/NFS
  - Snapshots and scheduled backups
  - Optionally: Plex, Docker, Tailscale

---

## 🛠️ Build Photos

> Images will be uploaded via my GitHub repo. Here is a PCPartPicker Link with my most up-to-date build - https://pcpartpicker.com/list/rjFHJn
---

## 📝 Future Plans

- Add side intake fan for HDD airflow
- Add UPS for power protection
- Create ZFS snapshot automation
- Add more drives via PCIe SATA card if needed more likley I will add more but to start this is all i can afford.

---

## 📚 Lessons Learned

- B550M board has only 4 SATA ports – may need a SATA expansion card for future drives  
- Front-to-back airflow is decent, but drive cage design slightly restricts front intake  
- Noctua P12 Redux is a great quiet fan with strong airflow – worth the price  

---


