---
title: Developer Reference — ERDs
description: Per-module entity-relationship diagrams, relationships, state machines, and design notes for the HMS Odoo 19 modules.
published: true
date: 2026-04-28T00:00:00.000Z
tags: hms, developer, erd, schema, home
editor: markdown
dateCreated: 2026-04-28T00:00:00.000Z
---

# Developer Reference — Entity Relationship Diagrams

Schema, relationships, and module internals for engineers extending the HMS codebase.

Source code: [reichie020212/odoo-hospital](https://github.com/reichie020212/odoo-hospital).

## Modules

| Module | What it covers |
|:-------|:---------------|
| [hms_base](/developer/erd/base) | Patients (`res.partner`), staff (`hr.employee`), specializations |
| [hms_appointment](/developer/erd/appointment) | Medical appointments on `calendar.event`, 5-state workflow |
| [hms_clinical](/developer/erd/clinical) | Consultations (EMR), vitals, prescriptions |
| [hms_lab](/developer/erd/lab) | Lab requests, panels, results, abnormal flagging |
| [hms_pharmacy](/developer/erd/pharmacy) | Dispensing via `stock.picking`, FEFO removal |
| [hms_billing](/developer/erd/billing) | Sale orders, invoices, insurance co-pay |
| [hms_inpatient](/developer/erd/inpatient) | Wards, beds, admissions, daily room-charge CRON |

## See also

- [Home](/home) — wiki landing page.
- [User guide](/user-guide/home) — task-oriented walkthroughs for staff.
