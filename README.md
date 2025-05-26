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
- **Client Scripts**: Auto-populate field values from Items table
- **Script Includes**:
  - Fine calculation logic
  - Utility & helper functions
- **UI Policies**:
  - Set item type (`Book`/`Ebook`)
  - Control field visibility
- **UI Actions**:
  - Request button (form banner) to initiate borrow flow
- **Business Rules**:
  - Fine calculators (per item/member)
  - Field validations and availability updates
- **Flow Designer**:
  - Notifications for borrowing events

---

## 🧬 Data Model

- Items Table (base info: Title, Author, etc.)
- Derived: Books, Ebooks, Issued Items
- Users: Staff, Members

---

## 🚀 Advanced Features (Future Scope)

- 🔍 **Search History**: Track books searched in past 30 days  
- 🎯 **Recommendation System**: ML-based personalized suggestions  
- 💳 **Subscription Model**: Premium features or access tiers  
- ⏰ **Scheduled Notifications**: Weekly engagement updates  
- 📊 **Library Stats**: Analytics via scheduled reports  

---

## 🎓 My Takeaways

- Learned to design scalable ServiceNow apps
- Gained deeper insights into ACL, UI scripting, and Flow Designer
- Understood importance of user-centric workflows and clean automation

---
