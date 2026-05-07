---
title: Demo Users
description: Ready-to-use demo logins for the Odoo 19 Hospital Management System — try the Doctor, Nurse, Manager, and Patient Portal roles without manual setup.
published: true
date: 2026-05-05T00:00:00.000Z
tags: hms, user-guide, demo, login
editor: markdown
dateCreated: 2026-05-05T00:00:00.000Z
---

# Demo Users

The HMS suite ships with demo accounts so you can explore each role immediately after installation. Sign in at your Odoo instance (e.g. `http://localhost:8069`) using any of the credentials below — the **login** and **password** are identical for each account.

> Demo accounts are intended for evaluation and local development only. Change the passwords (or disable the users) before exposing the instance to the internet.

## Accounts

| Role | Login | Password | What you can do |
|:-----|:------|:---------|:----------------|
| Admin | `hms_admin` | `hms_admin` | System administrator — full Odoo access including Settings, Users & Companies, technical menus, and every Hospital record. |
| Doctor | `hms_doctor` | `hms_doctor` | Run consultations, record vitals & prescriptions, request lab tests, dispense medicines, create invoice drafts. |
| Nurse | `hms_nurse` | `hms_nurse` | Check patients in, capture vitals, manage appointments and ward activity. |
| Manager | `hms_manager` | `hms_manager` | Full Hospital access: configuration (specializations, appointment types, lab tests, wards, beds, medicines), insurance policies, and all clinical/billing records. |
| Patient (portal) | `hms_patient` | `hms_patient` | Sign in at `/my` to view personal appointments and consultations (view-only). |

## Logging In

1. Open the Odoo login page (default: `http://localhost:8069/web/login`).
2. Enter one of the **logins** above as the email/username and the matching **password**.
3. Click **Log in**.
   - Staff accounts (Doctor, Nurse, Manager) land in the backend — open the app launcher and pick **Hospital**.
   - The Patient account lands on the portal at `/my`.

For the full walkthrough of each role's day-to-day workflows, see the [Getting Started](/user-guide/getting-started) guide.

## See also

- [Getting Started](/user-guide/getting-started) — end-to-end tour of the system.
- [User Guide home](/user-guide/home).
- [Features](/features) — overview of every capability in the suite.
