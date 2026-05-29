
# **Project Approach: AI in Healthcare – How AI Supports Doctors and Patients**  
**Members:** Sairaj Salkar & Harish Sable  
***

## 1. What Is This Project About?

This project is about understanding how **AI can help in healthcare**. AI supports doctors by making diagnosis faster, helps patients with health advice and reminders, and helps clinic staff by handling appointments.

**My goals:**
- Learn 6 main ways AI is used in healthcare
- Explain why AI should **help** doctors, not **replace** them
- Design a simple **medicine reminder chatbot**

***

## 2. 6 AI Use Cases in Healthcare

| # | Use Case | What AI Does | Who It Helps |
|---|----------|--------------|--------------|
| 1 | Disease Prediction | Predicts if someone might get diabetes/heart disease | Doctors, Patients |
| 2 | Medical Image Analysis | Reads X-rays, CT scans, MRIs to find problems | Doctors |
| 3 | Health Chatbots | Answers health questions 24/7 | Patients, Clinic Staff |
| 4 | Appointment Scheduling | Books and reminds patients for visits | Clinic Staff, Patients |
| 5 | Medicine Reminders | Sends reminders to take medicine on time | Patients, Doctors |
| 6 | Patient Record Analysis | Highlights important info in patient records | Doctors |

***

## 3. Why AI Should Assist, Not Replace Doctors

| Limitation | Simple Explanation |
|------------|-------------------|
| AI is not a doctor | AI can make mistakes. Only doctors can diagnose |
| Privacy matters | Patient data must stay private and secure |
| AI can be biased | May not work well for everyone |
| Doctors need understanding | Doctors should know WHY AI gave a suggestion |
| Human check needed | Doctor must review AI recommendations |

***

## 4. My Small Project: Medicine Reminder Chatbot

**Why I chose this:**
- Many patients forget medicine
- Simple to design
- Helps patients stay healthy
- Doctors can track adherence

***

### 4.1 Simple Chatbot Flow

```
[Patient Opens Chatbot]
        │
        ▼
  ┌───────────┐
  │ New User? │
  └─────┬─────┘
        │
   ┌────┴────┐
   │ NO │ YES
   ▼    ▼
Register  Login
   │    │
   └────┘
        │
        ▼
  ┌───────────┐
  │ Main Menu │
  └─────┬─────┘
        │
   ┌────┴────┬───────┬────────┐
   │1│ │2│ │3│ │4│
   ▼ ▼ ▼ ▼
View Update Skip Contact
Reminders Reminder Reminder Doctor
```

***

### 4.2 How It Works

1. **New users** register with name, phone, medicine details
2. **Old users** login with phone + OTP
3. Chatbot sends **daily reminders** via WhatsApp/SMS
4. Patients can: view reminders, update timing, skip, contact doctor

***

### 4.3 Sample Conversation

```
🤖 Bot: Hello! Welcome to MedReminder. New user?
👤 Patient: Yes

🤖 Bot: Enter your name:
👤 Patient: Sairaj Salkar

🤖 Bot: Enter phone number:
👤 Patient: 9876543210

🤖 Bot: How many medicines daily?
👤 Patient: 2

🤖 Bot: Medicine 1 (name, dosage, time):
👤 Patient: Metformin 500mg 8 AM

🤖 Bot: Medicine 2:
👤 Patient: Atorvastatin 10mg 9 PM

🤖 Bot: ✅ Saved! Reminders at 8 AM and 9 PM.

👤 Patient: Show tomorrow's reminders

🤖 Bot: Tomorrow:
   1. Metformin 500mg — 8:00 AM
   2. Atorvastatin 10mg — 9:00 PM

🤖 Bot: Take care! ❤️
```

***

## 5. Deliverables

| What I Submit | What It Is |
|---------------|-----------|
| Flowchart | Simple chatbot diagram |
| Explanation | 100-word description |
| Sample Conversation | Example chat |
| One-Page Report | This document |

***

## 6. What I Will Learn

- How AI is used in healthcare
- AI helping vs. replacing doctors
- How to design chatbot flow
- Why safety matters in medical AI
- How technology improves patient care

***

## 7. Simple Summary

| Who | How AI Helps |
|-----|--------------|
| **Doctors** | Faster diagnosis, less paperwork |
| **Patients** | 24/7 help, won't forget medicine |
| **Clinic Staff** | Fewer calls, fewer missed appointments |

**Conclusion:** AI makes healthcare better, but doctors stay in charge.
