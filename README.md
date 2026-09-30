# Swift Ship Tracker

## Phase 1: Requirement Analysis & Planning

### Project Overview

Customers often face delays and confusion while booking, tracking, and managing parcel deliveries because they need to contact customer support or use multiple applications.

**Swift Ship Tracker** aims to simplify the parcel delivery process by providing a conversational AI-powered solution where customers can:

- Book parcels
- Track shipments
- Receive delivery updates
- Manage delivery-related requests
- Get assistance through an AI agent

---

## Key Requirements

### 1. Requirement Gathering

Collect requirements from:

- Customers
- Delivery Agents
- Administrators

### 2. User Personas

The system will support three main user roles:

| User Role | Responsibilities |
|---|---|
| Customer | Book parcels, track shipments, view delivery status |
| Delivery Agent | Manage assigned deliveries and update delivery status |
| Admin | Manage customers, agents, parcels, and system operations |

### 3. Data Model

The Salesforce data model will define relationships between:

- Customer
- Parcel
- Sender
- Receiver
- Delivery Agent
- Delivery

Example relationship:

```text
Customer
   |
   └── Parcel
        |
        ├── Sender
        ├── Receiver
        └── Delivery
              |
              └── Delivery Agent


## Phase 1: Requirement Analysis & Planning

### 2: Gathering & Analysing User Needs

## 1. Users Involved

### Customers / Senders
- Book parcels
- Track deliveries
- Receive real-time delivery updates
- Get assistance through the portal or AI agent

### Delivery Agents
- View assigned parcels
- Update parcel delivery status
- Manage deliveries
- Ensure timely handover to customers

### Customer Support Team
- Handle delivery-related issues
- Respond to customer queries
- Assist customers with tracking and delivery problems
- Maintain smooth communication

### Admin Team
- Configure the Salesforce environment
- Manage user roles and permissions
- Configure security settings
- Monitor operational performance
- Manage reports and dashboards

### System Integrator / Developer
- Implement Salesforce automation
- Configure the AI Agent
- Develop integrations
- Maintain and test the system

---

## 2. Key Functional Needs

### Parcel Booking & Tracking
Customers should be able to book parcels and track their shipments through a Salesforce Experience Site or AI Agent.

### Real-Time Delivery Status

Delivery agents should be able to update parcel status in real time:

```text
Booked
   ↓
In Transit
   ↓
Out for Delivery
   ↓
Delivered

# Swift Ship Tracker

## Phase 1: Requirement Analysis & Planning

### Story 3: Identifying Key Salesforce Features & Tools Required

**Duration:** 5 minutes  
**Status:** In Progress  
**Assigned To:** Aswitha M

---

## 1. Salesforce Features Planned

### Custom Objects

The following custom objects will be created to manage parcel delivery information:

- `Parcel__c` – Stores parcel and shipment details
- `Delivery__c` – Stores delivery information and status
- `Sender__c` – Stores sender details
- `Receiver__c` – Stores receiver details

---

## 2. Standard Salesforce Objects

The following standard Salesforce objects will support the application:

| Object | Purpose |
|---|---|
| Account | Manage customer/company information |
| Contact | Store customer contact details |
| Case | Handle customer support issues |
| Task | Manage follow-up activities |
| EmailMessage | Maintain email communication |
| User | Manage Salesforce users and access |

---

## 3. Automation

Salesforce automation will reduce manual work and improve delivery operations.

### Record-Triggered Flows

Used to automatically perform actions when a Parcel or Delivery record is created or updated.

**Example:**

```text
Parcel Status Changed
        ↓
Record-Triggered Flow
        ↓
Send Customer Notification
        ↓
Update Related Delivery Information

# Swift Ship Tracker

## Phase 2: Data Model & Security

### Story 1: Designing Data Model and Security Model

**Duration:** 15 minutes  
**Status:** To Do  
**Assigned To:** Aswitha M

---

# 1. Data Model Design

The Swift Ship Tracker data model is designed to manage the complete parcel lifecycle from booking to delivery.

### Main Custom Objects

- `Parcel__c`
- `Delivery__c`
- `Sender__c`
- `Receiver__c`

---

## 2. Parcel__c

**Purpose:** Stores the core information about each parcel.

### Main Fields

| Field | Purpose |
|---|---|
| Parcel ID | Unique identifier for the parcel |
| Status | Current parcel status |
| Weight | Parcel weight |
| Estimated Delivery Date | Expected delivery date |
| Sender | Related sender |
| Receiver | Related receiver |

### Relationship

```text
Sender__c
    │
    │
    ▼
Parcel__c
    │
    │
    ├──────────► Receiver__c
    │
    ▼
Delivery__c

