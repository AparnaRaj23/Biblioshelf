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
