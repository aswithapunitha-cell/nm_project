# Swift Ship Tracker

## Phase 1: Requirement Analysis & Planning

**Epic Complexity:** Easy  
**Duration:** 50 minutes  
**Status:** In Progress

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

**Duration:** 15 minutes  
**Status:** In Progress  
**Assigned To:** Aswitha M

---

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

3. Delivery__c

Purpose: Stores delivery-specific information and tracks the parcel during transportation.

Main Fields
Field	Purpose
Delivery ID	Unique delivery identifier
Parcel	Related parcel
Current Location	Current delivery location
Estimated Delivery Date	Expected delivery date
Delivery Status	Current delivery status
Delivery Agent	Assigned delivery agent
Delivery Lifecycle
Booked
   ↓
In Transit
   ↓
Out for Delivery
   ↓
Delivered

Delivery agents can update the delivery status during the parcel lifecycle.

4. Sender__c

Purpose: Stores information about the person or organization sending the parcel.

Main Fields
Sender Name
Address
Contact Number
Email
Relationship
Sender__c
    │
    ├── Parcel 1
    ├── Parcel 2
    ├── Parcel 3
    └── Parcel N

A sender can be associated with multiple parcels.

Sender information can also be used for:

Booking confirmations
Delivery updates
Customer communication
5. Receiver__c

Purpose: Stores information about the person receiving the parcel.

Main Fields
Receiver Name
Address
Contact Number
Email
Relationship
Receiver__c
    │
    ├── Parcel 1
    ├── Parcel 2
    └── Parcel N

Receiver information is used for:

Delivery reference
Delivery confirmation
Automated notifications
6. Overall Data Model
                  ┌─────────────────┐
                  │   Sender__c     │
                  │                 │
                  │ Name            │
                  │ Address         │
                  │ Contact         │
                  │ Email           │
                  └────────┬────────┘
                           │
                           │
                           ▼
                  ┌─────────────────┐
                  │    Parcel__c    │
                  │                 │
                  │ Parcel ID       │
                  │ Status          │
                  │ Weight          │
                  │ Delivery Date   │
                  └───────┬─────────┘
                          │
             ┌────────────┴────────────┐
             │                         │
             ▼                         ▼
    ┌─────────────────┐       ┌─────────────────┐
    │  Receiver__c    │       │   Delivery__c   │
    │                 │       │                 │
    │ Name            │       │ Location        │
    │ Address         │       │ Status          │
    │ Contact         │       │ Delivery Date   │
    │ Email           │       │ Agent           │
    └─────────────────┘       └─────────────────┘
7. Security Model

Salesforce security will control which users can access objects, fields, and records.

Role Hierarchy
Administrator
      ↓
Delivery Manager
      ↓
Delivery Agent
      ↓
Customer

The hierarchy allows higher-level users to access appropriate records managed by users below them.

8. Profiles
Admin Profile

Provides administrative access to:

Parcel
Delivery
Sender
Receiver
Cases
Users
Reports
Configuration
Delivery Agent Profile

Provides access to:

View Parcel records
Update Delivery records
View Sender details
View Receiver details
Customer Profile

Customers should be able to view only their own parcel and delivery information through Experience Cloud.

Support Staff Profile

Provides access to:

Cases
Relevant Parcel information
Customer issue information

This allows support staff to resolve delivery-related issues.

9. Permission Sets

Permission Sets will provide additional permissions without creating separate profiles.

Example Permission Sets

Update Delivery Status

Allows authorized agents to update delivery status.

Access Agent Console

Provides additional access required by delivery agents.

User
  │
  ├── Profile
  │
  └── Permission Set
          │
          ▼
   Additional Access
10. Record-Level Security

Sharing Rules will control access to individual records.

Parcel__c

Agents and managers should receive access to the parcel records required for their work.

Delivery__c

Delivery records should be shared with the appropriate delivery agents and managers.

Customer Access

Customers should only be able to access records associated with their own sender/receiver information.

11. Field-Level Security

Sensitive information should have restricted access.

Restricted Fields
Sender Email
Receiver Contact Number
Location Coordinates

These fields should be accessible only to authorized Admin and Agent users.

                    Salesforce Security
                           │
        ┌──────────────────┼──────────────────┐
        ▼                  ▼                  ▼
   Object Access      Record Access      Field Access
    Profiles          Sharing Rules       FLS
    Permission Sets
12. Security Summary
Security Layer	Salesforce Feature
Object-Level	Profiles & Permission Sets
Record-Level	Role Hierarchy & Sharing Rules
Field-Level	Field-Level Security
Additional Access	Permission Sets
External Customer Access	Experience Cloud Security
Expected Outcome

After completing this story, the project will have:

Defined the Salesforce data model
Identified object relationships
Defined parcel and delivery lifecycle
Planned role hierarchy
Defined user profiles
Planned permission sets
Defined record-level sharing
Identified sensitive fields requiring Field-Level Security
