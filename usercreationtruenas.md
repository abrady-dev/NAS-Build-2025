# TrueNAS Scale: User Creation and Management Guide

This guide provides steps for creating users and managing permissions in TrueNAS Scale, based on the setup tutorial video.

## 1. Understanding the Basics

* **Pools:** Before creating users, ensure you have a storage pool set up. Pools are fundamental for storing data and managing permissions [00:01:00].
* **Data Sets:** Data sets are created within pools to organize data (e.g., for media, applications). Setting appropriate presets (like SMB for shares) during creation is important for access [00:07:00]. Nested data sets can help manage permissions more granularly [00:09:00].

## 2. Creating a User Account

1.  Navigate to the user management section in the TrueNAS Scale UI.
2.  Add a new user account [00:06:11].
3.  Fill in the necessary user details (username, password, etc.).

## 3. Managing Permissions

* **Groups:** Permissions are often best managed through groups [00:06:44].
* **Adding User to Groups:** Add the newly created user to relevant groups (e.g., the built-in `users` group) to grant access to shares or specific data sets [00:06:44].
* **Data Set Permissions:** Configure Access Control Lists (ACLs) or permissions on the specific data sets the user needs to access. Ensure the data set preset (e.g., SMB) aligns with the intended use [00:07:00].

## 4. Accessing Data

* Once the user is created and permissions are set on the relevant data sets, they should be able to access the designated shares or storage areas.

## 5. Data Protection Considerations (Optional but Recommended)

While not directly user creation, remember to configure:
* **Scrub Tasks:** For data integrity [00:10:53].
* **Snapshots:** For data recovery [00:11:59].
* **SMART Tests:** For drive health [00:13:33].

---

*This guide is based on the information presented in the TrueNAS Scale beginner's guide video.*