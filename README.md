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
