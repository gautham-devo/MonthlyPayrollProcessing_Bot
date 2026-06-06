<img width="1536" height="1024" alt="ChatGPT Image Jun 6, 2026, 05_02_05 PM" src="https://github.com/user-attachments/assets/3a934838-404f-41b8-b74a-bdae707398ac" />
<img width="864" height="1821" alt="ChatGPT Image Jun 6, 2026, 05_13_30 PM" src="https://github.com/user-attachments/assets/e8e4fb1a-bbc4-41c9-a3a2-2849728921f8" />

# 💰 CoreHR Payroll Processing Automation Bot

## Overview

An end-to-end Payroll Processing Automation developed using Automation Anywhere Community Edition.

The bot automatically processes monthly payroll after receiving a trigger email from HR. It validates employee attendance, performs salary calculations, updates payroll records in SQL Server, generates payroll reports, and sends personalized payslip emails to employees.

---

## Business Problem

CoreHR Pvt. Ltd. manually processed payroll for 80+ employees every month.

Manual process involved:

- Reading Employee Master Excel
- Reading Attendance Excel
- Calculating salaries manually
- Updating payroll sheets
- Updating SQL database
- Sending payslips individually

This consumed 2–3 working days and often introduced calculation errors.

---

## Solution

The Payroll Processing Bot automates the complete payroll lifecycle:

1. Reads payroll trigger email
2. Downloads payroll files
3. Reads employee and attendance data
4. Matches employees using EmpID
5. Performs 12 payroll calculations
6. Updates payroll result workbook
7. Inserts records into SQL Server
8. Sends personalized payslips
9. Sends HR summary report
10. Generates audit logs

---

## Technology Stack

- Automation Anywhere A360 Community Edition
- Excel Automation
- Email Automation (IMAP/SMTP)
- SQL Server
- DataTables
- Conditional Logic
- Error Handling
- Audit Logging

---

## Architecture

![Architecture](docs/payroll-architecture.png)

---

## Process Flow

![Process Flow](docs/process-flow.png)

---

## Bot Modules

### 1. readConfig.json

Responsibilities:

- Read configuration file
- Load email settings
- Load database connection string
- Load log path
- Load results path
- Retrieve credentials

---

### 2. emailConnect.json

Responsibilities:

- Connect to HR mailbox
- Detect payroll trigger email
- Extract month/year
- Validate attachments
- Download Excel files

---

### 3. excelActions.json

Responsibilities:

- Read Employee Master workbook
- Read Attendance workbook
- Create DataTables
- Validate numeric fields

---

### 4. excelSubActions.json

Responsibilities:

- Match employees using EmpID
- Build combined dataset
- Handle missing attendance records

---

### 5. operations.json

Responsibilities:

- Execute 12 salary calculations
- Calculate Gross Salary
- Calculate PF
- Calculate ESI
- Calculate PT
- Calculate TDS
- Calculate Net Salary
- Update payroll result sheet

---

### 6. database.json

Responsibilities:

- Prevent duplicate payroll runs
- Insert payroll records
- Update PayrollRuns status
- Store payroll summary statistics

---

### 7. finalEmailSending.json

Responsibilities:

- Generate employee payslip emails
- Send payroll summary to HR
- Create audit log
- Cleanup temporary files

---

## Salary Components Calculated

### Earnings

- Per Day Salary
- LWP Deduction Amount
- HRA
- DA
- Overtime Pay
- Gross Salary

### Deductions

- PF Deduction
- ESI Deduction
- Professional Tax
- TDS
- Salary Advance Deduction

### Final Output

- Net Salary

---

## Database Tables

### PayrollRuns

Tracks payroll execution status.

### PayrollDetails

Stores employee payroll records.

---

## Key Features

✔ Email Driven Trigger

✔ Dual Excel Processing

✔ EmpID Matching

✔ 12 Salary Calculations

✔ SQL Database Validation

✔ Duplicate Run Prevention

✔ Personalized Payslips

✔ HR Summary Reporting

✔ Audit Logging

✔ Error Recovery

---

## Outcome

Processing Time Reduced:

- Before: 2–3 Days
- After: < 15 Minutes

Accuracy Improved:

- Manual Formula Errors Eliminated
- Automated Validation Added

---

<div align="center">

### 🚀 DEVELOPED BY GAUTHAM JAYESH 🚀

**Automation Anywhere**

</div>
