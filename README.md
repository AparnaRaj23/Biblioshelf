# 📚 Biblioshelf

**A library management app to elevate your library experience with seamless organization and effortless book discovery.**

---

## 🧩 Problem Statement

The current library system suffers from manual workflows, leading to:
- Errors in issuing/returning books
- Difficulty tracking book availability
- Inefficient fine calculation
- Lack of real-time updates and notifications

---

## ✅ Implemented Solution

Biblioshelf streamlines and automates key library workflows:
- Automated & manual book issuing and returning
- Real-time book and ebook availability updates
- Member account management
- Fine calculation and overdue notifications

---

## 🛠️ Installation Guide

Follow these steps to install the **📚 Biblioshelf** app in your ServiceNow instance from GitHub using **Source Control Integration**.

---

### 🌐 Prerequisites

- A GitHub repository with the application code pushed
- A ServiceNow Developer Instance
- `admin` role access on the instance

---

### 🔐 1. Create a GitHub Credential in ServiceNow

Before linking to GitHub, create a credential to allow ServiceNow to access your GitHub repo:

1. Navigate to **System Definition → Credentials**
2. Click **New**
3. Choose **Basic Auth Credentials**
4. Fill in:
   - **Name**: e.g., `GitHub Biblioshelf`
   - **Username**: Your GitHub username
   - **Password**: Your GitHub [personal access token](https://github.com/settings/tokens) (not your GitHub password)
5. Click **Submit** ✅

---

### 🧩 2. Link App to GitHub via Studio

1. Open **Studio** (`System Applications → Studio`)
2. In the **Application Picker**, choose or create the `Biblioshelf` app
3. Click **Source Control → Link to Source Control** 🔗
4. Fill in:
   - **Repository URL**: `https://github.com/your-username/your-repo-name.git`
   - **Branch**: e.g., `main`
   - **Credential**: Select the credential you just created (`GitHub Biblioshelf`)
5. Click **Link to Source Control** and wait for the sync to complete

📘 **Reference**: Official ServiceNow guide on [Linking to Source Control](https://developer.servicenow.com/dev.do#!/learn/courses/xanadu/app_store_learnv2_rest_xanadu_rest_integrations/app_store_learnv2_rest_xanadu_data_stream_actions/app_store_learnv2_rest_xanadu_exercise_save_your_world_glaciers_spoke_work_optional)

---

### 🧪 3. Post-Installation Checklist

- ✅ Use **Studio** to verify that all tables, flows, and scripts have synced
- 👥 Test access controls by impersonating both a **Staff** and **Member**
- ✉️ Ensure notifications are configured properly for overdue alerts
- 🔍 Use **Flow Designer → Test → Execution Details** to troubleshoot automation

---

### 💡 Pro Tips

- 🧭 Use **Application Picker** to stay within the correct app scope
- 📚 Use `Books`, `Ebooks`, and `Issued Items` to seed your library with test data
- 🧠 Maintain your source control repo for versioning and team collaboration

---

## 👥 User Personas

### 1. Staff
- Manages book inventory
- Approves/rejects borrowing requests
- Issues/returns books
- Manages ebook status and availability
- Sends overdue notifications

### 2. Member
- Explores and requests books/ebooks
- Checks availability
- Returns borrowed items
- Receives/pays overdue fines

---

## 🔒 Access Control (ACL)

| Role   | Permissions |
|--------|-------------|
| Member | Access only to Books & Ebooks tables, can request items |
| Staff  | Access to all tables *except* the Staff table |
| Admin  | All staff rights + ability to delete records |

---

## 🛠️ Components Used

- **User Table Extensions**: Custom Member & Staff tables
- **Client Scripts**:
  - Auto-populate field values in `Books`, `Ebooks`, and `Issued Item` tables from the `Items` table (e.g., Title, Author, etc.)
  - **Auto-update logic**: Automatically updates the following when a book is issued:
    - `No. of Copies Available`
    - `No. of Books Allowed`
- **Field control logic**:
  - Sets `Item Type` to `'Book'` or `'Ebook'` based on the item
  - Makes certain fields read-only based on context to ensure data integrity
- **Script Includes**:
  - Fine calculation logic
  - Utility & helper functions
- **UI Policies**:
  - Control field visibility
- **UI Actions**:
  - Request button (form banner) to initiate book borrow flow
- **Business Rules**:
  - Fine calculators (per item/member)
  - Field validations and availability updates
  - Field validations 
- **Flow Designer**:
  - Notifications for borrowing events

---

## 🧬 Data Model

- Items Table (base info: Title, Author, etc.)
- Derived: Books, Ebooks
-  Issued Items
- Users: Admin, Staff, Members

---

## 🚀 Advanced Features (Future Scope)

- 🔍 **Search History**: Track books searched in past 30 days  
- 🎯 **Recommendation System**: ML-based personalized suggestions  
- 💳 **Subscription Model**: Premium features or access tiers  
- ⏰ **Scheduled Notifications**: Weekly engagement updates  
- 📊 **Library Stats**: Analytics via scheduled reports  
