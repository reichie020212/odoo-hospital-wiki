---
title: Hospital Management System
description: Wiki for the Odoo 19 Hospital Management System (HMS) — user guide, feature overview, and developer reference.
published: true
date: 2026-05-05T00:00:00.000Z
tags: hms, odoo, hospital, home
editor: markdown
dateCreated: 2026-04-26T00:00:00.000Z
---

# Hospital Management System

A suite of **7 Odoo 19 Community Edition modules** covering the full patient lifecycle: patient & staff records, appointments, EMR consultations, laboratory, pharmacy dispensing, billing with insurance co-pay, inpatient wards & beds, a self-service patient portal, and a public hospital website.

> **New here?** See the [Features →](/features) page for an at-a-glance list of everything the suite does.

Source code: [reichie020212/odoo-hospital](https://github.com/reichie020212/odoo-hospital).

## User guide

- [Getting Started](/user-guide/getting-started) — end-to-end tour of the system, from logging in to billing and the patient portal.

## Developer reference

Per-module entity-relationship diagrams (ERDs), relationships, state machines, and design notes:

| Module | What it covers |
|:-------|:---------------|
| [hms_base](/developer/erd/base) | Patients (`res.partner`), staff (`hr.employee`), specializations |
| [hms_appointment](/developer/erd/appointment) | Medical appointments on `calendar.event`, 5-state workflow |
| [hms_clinical](/developer/erd/clinical) | Consultations (EMR), vitals, prescriptions |
| [hms_lab](/developer/erd/lab) | Lab requests, panels, results, abnormal flagging |
| [hms_pharmacy](/developer/erd/pharmacy) | Dispensing via `stock.picking`, FEFO removal |
| [hms_billing](/developer/erd/billing) | Sale orders, invoices, insurance co-pay |
| [hms_inpatient](/developer/erd/inpatient) | Wards, beds, admissions, daily room-charge CRON |

## How this wiki is organized

- **[`/features`](/features)** — at-a-glance list of every capability (and current limitations).
- **[`/user-guide/`](/user-guide/home)** — task-oriented walkthroughs for staff using the system.
- **[`/developer/`](/developer/erd/home)** — schema, relationships, and module internals for engineers extending the codebase.
