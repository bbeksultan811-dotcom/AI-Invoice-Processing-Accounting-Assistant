# AI Invoice Processing Assistant

<p align="center">
  <img src="screenshots/workflow.png" width="900">
</p>

<p align="center">
AI-powered invoice processing workflow built with <b>n8n</b>, <b>Gemini AI</b>, <b>Supabase</b>, <b>Google Sheets</b>, and <b>Gmail</b>.
</p>

---

# Business Problem

Companies receive invoices every day from suppliers.

Accounting teams often spend significant time:

- Opening invoices manually
- Extracting invoice information
- Entering data into spreadsheets
- Saving records to databases
- Sending confirmation emails

Manual processing is slow, repetitive, and prone to human error.

---

# Solution

This workflow automates the entire invoice processing pipeline.

The system:

- Receives invoice data
- Uses Gemini AI to extract structured information
- Validates extracted fields
- Stores data in Supabase
- Logs invoices in Google Sheets
- Sends confirmation emails
- Returns a structured API response

---

# Features

- AI invoice extraction
- Structured JSON parsing
- Invoice validation
- Supabase integration
- Google Sheets integration
- Gmail notifications
- Error handling
- Conditional workflow logic
- API response handling
- Modular workflow architecture

---

# Tech Stack

- n8n
- Gemini AI API
- Supabase
- Google Sheets API
- Gmail API
- JavaScript
- Webhooks

---

# Workflow Overview

```text
Webhook
      │
      ▼
Edit Fields
      │
      ▼
Gemini AI
      │
      ▼
Parse JSON
      │
      ▼
Validate Invoice
      │
      ▼
Invoice Valid?
      │
 ┌────┴────────────┐
 │                 │
 ▼                 ▼
TRUE             FALSE
 │                 │
 ▼                 ▼
Supabase      Validation Error
 │                 │
 ▼                 ▼
Google Sheets  Gmail (Error)
 │
 ▼
Gmail (Success)
 │
 ▼
Respond to Webhook
```

---

# Project Structure

```text
.
├── README.md
├── workflow.json
└── screenshots
    ├── workflow.png
    ├── webhook-test.png
    ├── gemini-output.png
    ├── supabase-table.png
    ├── google-sheets.png
    └── success-email.png
```

---

# Screenshots

| Workflow | Gemini Output |
|-----------|---------------|
| <img src="screenshots/workflow.png" width="100%"> | <img src="screenshots/gemini-output.png" width="100%"> |

| Supabase | Google Sheets |
|-----------|---------------|
| <img src="screenshots/supabase-table.png" width="100%"> | <img src="screenshots/google-sheets.png" width="100%"> |

| Email | Webhook Test |
|--------|--------------|
| <img src="screenshots/success-email.png" width="100%"> | <img src="screenshots/webhook-test.png" width="100%"> |

---

# Example Invoice

```text
Invoice Number: INV-2026-001

Vendor: Amazon Web Services

Invoice Date: 2026-07-17

Due Date: 2026-08-17

Currency: USD

Subtotal: 250.00

VAT: 50.00

Total: 300.00
```

---

# AI Output

```json
{
  "invoice_number": "INV-2026-001",
  "vendor": "Amazon Web Services",
  "invoice_date": "2026-07-17",
  "due_date": "2026-08-17",
  "currency": "USD",
  "subtotal": 250,
  "vat": 50,
  "total": 300
}
```

---

# Validation Logic

The workflow validates:

- Required fields
- Invoice number
- Vendor name
- Invoice date
- Currency
- Positive subtotal
- Positive VAT
- Positive total

If validation fails:

- Invoice is not saved
- Error email is sent
- API returns an error response

---

# API Response

### Success

```json
{
  "success": true,
  "message": "Invoice processed successfully.",
  "invoice_number": "INV-2026-001",
  "vendor": "Amazon Web Services",
  "total": 300
}
```

### Validation Error

```json
{
  "success": false,
  "message": "Invoice validation failed.",
  "errors": [
    "Missing vendor",
    "Invalid total amount"
  ]
}
```

---

# Business Benefits

- Eliminates manual invoice entry
- Reduces processing time
- Improves data accuracy
- Automates accounting workflows
- Stores invoices centrally
- Creates structured financial records
- Reduces repetitive administrative work

---

# Challenges Solved

During development the workflow addressed several real-world automation challenges:

- AI response formatting
- JSON parsing
- Data validation
- Conditional workflow routing
- API integration
- Database persistence
- Spreadsheet synchronization
- Email automation
- Structured API responses
- Modular workflow design

---

# Possible Improvements

- PDF upload support
- OCR document extraction
- Duplicate invoice detection
- ERP integration
- QuickBooks integration
- Xero integration
- Approval workflow
- Slack notifications
- Invoice status tracking
- Multi-currency support
- Automatic tax calculation

---

# Skills Demonstrated

- AI Automation
- Invoice Processing
- Prompt Engineering
- API Integration
- Workflow Design
- JavaScript
- JSON Parsing
- Data Validation
- Supabase
- Google Sheets
- Gmail Automation
- Business Process Automation
- Error Handling
- REST API Design

---

# Repository Contents

- Complete n8n workflow
- Project documentation
- Workflow screenshots
- Architecture overview
- Example invoice
- AI extraction example
- Validation logic
- API response examples

---

# Author

Built by **Zvc Qds** as part of an AI Automation Engineering portfolio.
