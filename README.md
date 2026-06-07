# Medical Appointment No-Shows — Data Analysis & Dashboard

An end-to-end analytics project exploring why patients miss medical appointments, using a dataset of ~107,000 appointments. The project covers the full workflow: data cleaning and feature engineering in Python, followed by an interactive dashboard in Tableau.

## 🔗 Live Dashboard
**[View the interactive dashboard on Tableau Public](https://public.tableau.com/views/MedicalAppointmentNo-Shows_17808379119100/MedicalAppointmentNo-Shows)**

## 📊 Project Overview
The goal was to understand the drivers of appointment no-shows and identify which patients and conditions carry the highest risk. As a pharmacist, this question matters to me directly — missed appointments often mean missed monitoring and weaker follow-up for chronic patients.

The analysis answers questions like:
- How does the waiting time between booking and appointment affect attendance?
- Do SMS reminders actually reduce no-shows?
- Which age groups and patient types are most likely to miss appointments?
- Where are the geographic hotspots for no-shows?

## 🛠️ Tools & Techniques
- **Python (pandas)** — data cleaning, type standardization, feature engineering
- **Jupyter Notebook** — documented, step-by-step data preparation
- **Tableau** — interactive dashboard with KPIs and seven views
- **Tableau Public** — publishing and sharing

## 🐍 Data Preparation (Python)
Key steps in [`Medical_appointment_Noshow.ipynb`](Medical_appointment_Noshow.ipynb):
- Standardized column names and corrected data types (including treating patient ID as an identifier, not a number)
- Removed invalid records (appointments with negative waiting time)
- Engineered features: waiting time and waiting-time categories, age groups, calendar features (month, weekday), and clinical risk flags
- Built a **leak-free no-show history** — each patient's prior no-shows are counted using only earlier appointments, so the current visit never leaks into its own history
- Exported a clean dataset ready for visualization

## 📈 Key Findings
- **Waiting time is the strongest driver.** No-show rates climb from under 5% for same-day appointments to over 30% for the longest waits.
- **SMS reminders are a statistical trap.** Patients who received an SMS missed *more* often — but reminders are mainly sent when there's already a long wait, so the wait drives the gap, not the reminder.
- **Clinically high-risk patients are the most reliable.** Elderly patients with chronic conditions attended *more* consistently than average, not less.
- Adolescents had the highest no-show rate of any age group; seniors the lowest.

## 📁 Repository Contents
| File | Description |
|------|-------------|
| `Medical_appointment_Noshow.ipynb` | Python notebook: data cleaning and feature engineering |
| `healthcare_noshows_appt.csv` | Dataset used in the analysis |

## 📚 Data Source
Based on the [Medical Appointment No Shows dataset](https://www.kaggle.com/datasets/joniarroba/noshowappointments) (Kaggle).

---
*Built by Jessica el Khouri— pharmacist specialized healthcare data analytics.*
