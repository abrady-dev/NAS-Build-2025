# TrueNAS Scale: User Creation and Management Guide

This guide provides steps for creating users and managing permissions in TrueNAS Scale.

## 1. Understanding the Basics

* **Pools:** Before creating users, ensure you have a storage pool set up. Pools are fundamental for storing data and managing permissions.
* **Data Sets:** Data sets are created within pools to organize data (e.g., for media, applications). Setting appropriate presets (like SMB for shares) during creation is important for access. Nested data sets can help manage permissions.

## 2. Creating a User Account

1.  Navigate to the user management section in the TrueNAS Scale UI.
2.  Add a new user account
3.  Fill in the necessary user details (username, password, etc.).

## 3. Managing Permissions

* **Groups:** Permissions are often best managed through groups.
* **Adding User to Groups:** Add the newly created user to relevant groups (e.g., the built-in `users` group) to grant access to shares or specific data sets
* **Data Set Permissions:** Configure Access Control Lists (ACLs) or permissions on the specific data sets the user needs to access. Ensure the data set preset (e.g., SMB) aligns with the intended use

## 4. Accessing Data

* Once the user is created and permissions are set on the relevant data sets, they should be able to access the designated shares or storage areas.

## 5. Data Protection Considerations (Optional but Recommended)

While not directly user creation, remember to configure:
* **Scrub Tasks:** For data integrity
* **Snapshots:** For data recovery
* **SMART Tests:** For drive health

---
For my use case, I created two users myself and my father. 
