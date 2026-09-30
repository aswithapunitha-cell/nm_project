# 🚚 Swift Ship Tracker

## Salesforce Parcel Delivery Management System

Swift Ship Tracker is a Salesforce-based parcel delivery management
system designed to manage the complete parcel lifecycle from booking
to delivery confirmation.

The system combines Salesforce CRM, Flow Automation, Apex,
Experience Cloud, Agentforce AI, Prompt Builder, Email Alerts,
Security, Reports, and Dashboards.

---

# 🎯 Project Objective

Customers often face delays and confusion while booking, tracking,
and managing parcel deliveries because they need to contact support
or use multiple applications.

Swift Ship Tracker provides a centralized Salesforce solution where
customers can:

- Book parcels
- Track shipments
- Receive delivery updates
- Manage sender and receiver information
- Get AI-powered assistance

---

# 👥 Users Involved

| User | Responsibilities |
|---|---|
| Customer / Sender | Book parcels, track deliveries, receive updates |
| Delivery Agent | Manage assigned parcels and update delivery status |
| Customer Support | Handle delivery issues and customer queries |
| Admin | Manage users, security, configuration and reports |
| Developer / Integrator | Implement automation, AI and integrations |

---

# 🏗️ Project Architecture

```text
                    SWIFT SHIP TRACKER
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v
    Customer          Delivery Agent        Admin
        |                  |                  |
        +------------------+------------------+
                           |
                           v
                    SALESFORCE CRM
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v
    Data Model         Automation             AI
        |                  |                  |
        v                  v                  v
   Custom Objects       Flows            Agentforce
   Standard Objects     Apex             Prompt Builder
                        Email Alerts
        |
        v
 Reports & Dashboards

