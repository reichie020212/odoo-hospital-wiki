---
title: Features
description: At-a-glance list of everything the Odoo 19 Hospital Management System suite does, plus current known limitations.
published: true
date: 2026-05-05T00:00:00.000Z
tags: hms, features, overview
editor: markdown
dateCreated: 2026-05-05T00:00:00.000Z
---

# Features

A complete tour of what the Hospital Management System (HMS) suite delivers, grouped by capability. For deeper walkthroughs, see the [User Guide](/user-guide/home); for schema and internals, see the [Developer Reference](/developer/erd/home).

## Table of Contents

- [1. Patient & Staff Records](#1-patient--staff-records)
- [2. Appointment Scheduling](#2-appointment-scheduling)
- [3. Electronic Medical Records (EMR) / Consultations](#3-electronic-medical-records-emr--consultations)
- [4. Laboratory](#4-laboratory)
- [5. Pharmacy / Dispensing](#5-pharmacy--dispensing)
- [6. Inpatient / Wards & Beds](#6-inpatient--wards--beds)
- [7. Billing (Direct Pay)](#7-billing-direct-pay)
- [8. Insurance & Co-Pay](#8-insurance--co-pay)
- [9. Patient Portal (Self-Service)](#9-patient-portal-self-service)
- [10. Public Website](#10-public-website)
- [11. Cross-Cutting Capabilities](#11-cross-cutting-capabilities)
- [Known Limitations](#known-limitations)

---

## 1. Patient & Staff Records

- Patient demographics: date of birth, age, gender, blood group, guardians.
- Auto-generated patient reference numbers (`P/2026/00001`).
- Doctor & nurse profiles with specializations and license numbers.
- Master list of medical specializations (General Medicine, Pediatrics, Cardiology, OB/GYN, Orthopedics, Dermatology).
- Role-based security: Hospital User, Hospital Manager, Pharmacy User, Lab Technician.

## 2. Appointment Scheduling

- Medical appointments separated from generic staff calendars.
- 5-state workflow: **Draft → Confirmed → Checked-in → Done → Cancelled**.
- Color-coded calendar view by status, plus list and form views.
- Configurable appointment types (General Consultation, Follow-up, Vaccination) with default durations.

## 3. Electronic Medical Records (EMR) / Consultations

- Full consultation record per visit with auto-numbered reference (`CONS/2026/05/0001`).
- Chief complaint, history, examination, diagnosis, treatment plan.
- Vital signs: BP, heart rate, temperature, SpO₂, weight, height, auto-computed BMI.
- Prescription lines with dosage, frequency, duration, instructions.
- Medical history page on the patient record, plus chatter and follow-up activities.
- Doctor-level write protection (doctors edit only their own consultations).

## 4. Laboratory

- Lab test catalog with units, normal ranges, and panel hierarchies (e.g. CBC → WBC, RBC, Platelets, Hematocrit).
- Lab requests linked to patient, doctor, and consultation.
- 5-state workflow: **Draft → Sample Collected → Processing → Done → Cancelled**.
- One-click panel expansion into individual result lines.
- Automatic abnormal-value flagging based on normal range.
- Dedicated Lab Technician role.

## 5. Pharmacy / Dispensing

- `Medicine` flag on products, plus a dedicated **Medicines** configuration menu.
- "Dispense" button on consultations creates an outgoing stock picking.
- FEFO (First-Expiry-First-Out) removal strategy with lot/expiry tracking.
- Prescription lines automatically marked **Dispensed** when the picking is validated.
- Dedicated Pharmacy User role.

## 6. Inpatient / Wards & Beds

- Wards with floor and gender-restriction settings.
- Beds with type (Standard, Semi-Private, Private, ICU) and live status (Available, Occupied, Cleaning, Maintenance).
- Admissions workflow: **Draft → Admitted → Discharged**, with diagnosis, notes, and chatter.
- Auto-numbered admissions (`ADM/2026/05/0001`).
- Daily room-charge CRON automatically posts the per-day fee to the patient's bill.
- Discharge releases the bed back to **Available**.

## 7. Billing (Direct Pay)

- One-click "Create Invoice Draft" on completed consultations.
- Generates a draft Sale Order using the service product on the appointment type.
- "Billed" ribbon prevents double-invoicing.
- Smart buttons to view the linked Sale Order and Invoices.
- **Lab Billing bridge:** bills lab tests (panels expanded) on a completed lab request.
- **Pharmacy Billing bridge:** dispensed medicines auto-added to the consultation's Sale Order on picking validation.

## 8. Insurance & Co-Pay

- Mark partners as Insurance Companies.
- Insurance policies per patient with coverage % (default 80%), validity dates, individual or corporate type.
- Automatic co-pay split: when billing a consultation, a negative "Insurance Discount" line is added to the Sale Order so the patient only pays the co-pay.

## 9. Patient Portal (Self-Service)

- Patients log in at `/my` to view:
  - **My Appointments** — date, doctor, type, status.
  - **My Consultations** — diagnosis, vitals, prescriptions.
  - Counters on the portal homepage.
- Strict record rules: each patient sees only their own data.
- View-only (no online booking yet — see [Known Limitations](#known-limitations)).

## 10. Public Website

- `/hospital` — homepage with hero section, services, and doctor cards.
- `/hospital/doctors` — published doctor profiles with photo, specialization, bio.
- `/hospital/services` — published medical services and durations.
- `/hospital/contact` — address, phone, email, operating hours pulled from company info.
- Per-doctor and per-service "Publish on Website" toggle.

## 11. Cross-Cutting Capabilities

- Audit trail (chatter) on consultations, lab requests, and admissions.
- Follow-up activities and reminders on EMR records.
- Auto-generated sequences for patients, consultations, lab requests, admissions, dispensing pickings.
- Demo data ready out of the box: ready-to-use logins for Doctor, Nurse, Manager, Pharmacy, Lab Tech, and a Patient Portal account.
- Containerized deployment (Docker Compose, dev + prod) with PostgreSQL 16.
- 140+ automated tests guarding the workflows.

---

## Known Limitations

- No online appointment booking from the public site yet — patients must call/visit; portal is view-only.
- Insurer-side invoicing (collecting the insurance company's share) is not automated.
- Pre-authorization workflow for insurance is not yet built.
- Lab results are not exposed in the patient portal (today only appointments and consultations are).
- Bed transfers mid-admission require discharge + re-admission.
- Multi-warehouse / satellite pharmacies are not supported (single central pharmacy only).

## See also

- [Home](/home) — wiki landing page.
- [User Guide](/user-guide/home) — task-oriented walkthroughs for staff.
- [Developer Reference](/developer/erd/home) — schema and module internals.
