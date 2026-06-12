# 🚀 AI-Powered Event Management & RSVP Platform

> A complete AI-driven Event Management System that automates event creation, RSVP registration, ticket generation, QR verification, email notifications, and analytics.

## 📖 Overview

This platform combines the functionality of **Eventbrite + Google Forms + AI Assistant** into a single system.

### Modules
- 🌐 Public Event Website
- 🤖 AI Event Creation Agent
- 📝 Dynamic RSVP System
- 🎟 Ticket Generation Engine
- 📱 QR Verification System
- 📧 Email Notification Service
- 👨‍💼 Admin Dashboard
- 📊 Analytics Dashboard

---

# 🏗 Overall System Architecture

```text
Admin
   │
   ▼
AI Agent
   │
   ▼
Backend APIs
   │
   ▼
Database
   │
   ├── Public Website
   ├── Admin Dashboard
   ├── Ticket Service
   ├── Email Service
   └── QR Verification
```

---

# 🤖 AI Agent Architecture

The AI Agent converts natural language prompts into structured actions.

Example Prompt:

> Create an AI Workshop on 20 July at VJIT Auditorium with capacity 300 and ticket price ₹199.

```text
Admin Prompt
      │
      ▼
Prompt Interpreter
      │
      ▼
Information Extractor
      │
      ▼
Validation Engine
      │
      ▼
Action Decision Engine
      │
      ▼
Backend API Calls
      │
      ▼
Database + Website
```

---

# 📝 RSVP Architecture

```text
User
 │
 ▼
Open Event
 │
 ▼
Click Register
 │
 ▼
Dynamic RSVP Form
 │
 ▼
Validate Details
 │
 ▼
Store Registration
 │
 ▼
Generate Ticket ID
 │
 ▼
Generate QR
 │
 ▼
Send Email
 │
 ▼
Registration Complete
```

---

# 🎟 Ticket Generation Architecture

```text
Registration Success
      │
      ▼
Generate Unique Ticket ID
      │
      ▼
Generate QR Code
      │
      ▼
Create Digital Ticket
      │
      ▼
Store Ticket
      │
      ▼
Send Ticket to Email
```

---

# 📧 Email Service Architecture

```text
Registration
      │
      ▼
Fetch Event Details
      │
      ▼
Generate Ticket
      │
      ▼
Attach QR Code
      │
      ▼
Compose Email
      │
      ▼
Send Email
      │
      ▼
User Inbox
```

---

# 📱 QR Verification Architecture

```text
Volunteer Device
      │
      ▼
Open Scanner
      │
      ▼
Scan QR
      │
      ▼
Extract Ticket ID
      │
      ▼
Verify API
      │
      ▼
Search Database
      │
      ▼
Ticket Valid?
      │
 ┌────┴────┐
 │         │
Yes        No
 │         │
 ▼         ▼
Already?  Invalid
 │
┌──┴───┐
│      │
No     Yes
│      │
▼      ▼
Allow  Already Checked In
Entry
│
▼
Mark Attendance
```

---

# 👨‍💼 Admin Dashboard Architecture

```text
Admin Login
      │
      ▼
Dashboard
      │
      ├── Create Event
      ├── Edit Event
      ├── Delete Event
      ├── View Registrations
      ├── Attendance
      ├── Export CSV
      ├── Analytics
      └── Settings
```

---

# 🗄 Database Tables

## Admins
- admin_id
- name
- email
- password
- role

## Events
- event_id
- title
- description
- venue
- date
- time
- capacity
- price
- status

## Users
- user_id
- name
- email
- phone

## Registrations
- registration_id
- event_id
- user_id
- ticket_id
- payment_id
- status

## Tickets
- ticket_id
- event_id
- ticket_code
- qr_code
- created_at

## Attendance
- attendance_id
- ticket_id
- checked_in
- checked_in_at

## Payments
- payment_id
- registration_id
- amount
- status
- payment_method

---

# 🌐 Public Website Flow

```text
Home
  │
  ▼
Events
  │
  ▼
Event Details
  │
  ▼
Register
  │
  ▼
Success
  │
  ▼
My Ticket
```

---

# 👤 User Flow

```text
Visit Website
      │
      ▼
Browse Events
      │
      ▼
Open Event
      │
      ▼
Register
      │
      ▼
Validation
      │
      ▼
Registration Stored
      │
      ▼
Ticket Generated
      │
      ▼
QR Generated
      │
      ▼
Email Sent
      │
      ▼
Receive Ticket
      │
      ▼
Attend Event
      │
      ▼
QR Verification
      │
      ▼
Entry Allowed
```

---

# 👨‍💼 Organizer Flow

```text
Login
  │
  ▼
Enter Prompt
  │
  ▼
AI Agent
  │
  ▼
Create Event
  │
  ▼
Website Updated
  │
  ▼
Registration Opens
  │
  ▼
Users Register
  │
  ▼
Dashboard Updates
  │
  ▼
Analytics
```

---

# 🔥 Features

## User
- Browse Events
- Register
- Receive Ticket
- Receive QR
- View Registration Status

## Admin
- Create/Edit/Delete Events
- View Registrations
- Attendance Management
- Export CSV
- Analytics Dashboard

## AI Agent
- Prompt Understanding
- Event Creation
- RSVP Generation
- Ticket Configuration
- Email Configuration

## Ticket System
- Unique Ticket IDs
- QR Code Generation
- Digital Tickets
- Verification

## Verification
- QR Scan
- Ticket ID Search
- Email Search
- Phone Search
- Duplicate Prevention

---

# 📈 End-to-End Flow

```text
Admin
  │
  ▼
AI Prompt
  │
  ▼
AI Agent
  │
  ▼
Backend APIs
  │
  ▼
Database
  │
  ▼
Website Published
  │
  ▼
Users Register
  │
  ▼
Registration Stored
  │
  ▼
Ticket Generated
  │
  ▼
QR Generated
  │
  ▼
Email Sent
  │
  ▼
User Receives Ticket
  │
  ▼
Event Day
  │
  ▼
QR Scan
  │
  ▼
Database Verification
  │
  ▼
Attendance Recorded
  │
  ▼
Analytics Updated
```

---

# 🛠 Planned Tech Stack

- Next.js
- Tailwind CSS
- TypeScript
- Supabase/PostgreSQL
- Node.js
- Resend Email API
- QR Code Generator
- Vercel
- AI Agent (LLM + Backend Tools)

---

# 🎯 Vision

The organizer should be able to type:

> "Create a 24-hour Hackathon on 15 August at VJIT with capacity 500 and ₹299 registration fee."

The platform will automatically:
- Create the event
- Publish the event page
- Generate the RSVP form
- Open registrations
- Generate tickets
- Generate QR codes
- Send confirmation emails
- Verify attendees on event day
- Update analytics in real time

```text
One Prompt
     │
     ▼
AI Agent
     │
     ▼
Entire Event Platform Configured Automatically
```
