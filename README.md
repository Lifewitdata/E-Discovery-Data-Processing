# 📂 E-Discovery Data Processing and Analysis Pipeline


This project demonstrates an **end-to-end simulated e-discovery workflow** using Python. It covers the entire lifecycle: generating a large dataset of email records → processing → cleaning → storing → analyzing → reporting → visualization.

---

## 🎯 Project Goal
Showcase a robust **data pipeline** for handling **Electronically Stored Information (ESI)** in legal contexts.  
Focus areas:
- Data normalization & quality assurance  
- Text preprocessing with NLP  
- Insightful analytics & visual dashboards  

---

## 📜 Description
**E-discovery (electronic discovery)** involves identifying, processing, and producing electronically stored information (ESI) for legal use.  
This notebook simulates those steps, providing a **framework for managing large-scale document metadata and text** efficiently.

---

## ✨ Key Features
- 🔹 **Synthetic Data Generation** with `Faker` (~50,000 records)  
- 🔹 **Normalized Relational Database Schema** using `SQLAlchemy` + SQLite  
- 🔹 **Data Cleaning** (null handling, duplicates, date standardization)  
- 🔹 **NLP Preprocessing** (tokenization, stopword removal, punctuation cleaning via `NLTK`)  
- 🔹 **Automated QA Checks** with error logging into an `Error_Log` table  
- 🔹 **Analytics & Visualization** (`Matplotlib` + `Seaborn`)  
- 🔹 **Multi-format Export** (`CSV`, `Parquet`, `JSON`)  

---

## ⚙️ Workflow Overview
1. **Setup** → Import libraries & initialize DB  
2. **Data Generation** → Create fake dataset (`Faker`)  
3. **Database & ETL** → Normalize & load into SQL tables  
4. **Cleaning & Preprocessing** → Fix missing values & clean text  
5. **Quality Checks** → Log issues into `Error_Log`  
6. **Analysis & Visualization** → Build analytical dashboard  
7. **Export** → Save outputs in multiple formats  

---

## 🗂️ Database Schema
**Tables:**  
- **`Documents`** → Metadata (`Document ID`, `Date`, `File Type`)  
- **`Custodians`** → Custodian info (`Custodian ID`, `Name`)  
- **`Emails`** → Core email data (`Email ID`, linked to `Documents` & `Custodians`)  
- **`Error_Log`** → QA issues (`Error ID`, `Document ID`, `Error Type`)  

---

## 📊 Visualization Dashboard
Final 2x2 dashboard includes:  
- Email volume trends  
- Custodian distributions  
- Document type breakdown  
- Error log summaries  

---

## 🛠️ Tech Stack
- **Python 3**  
- **Pandas** – Data manipulation  
- **SQLAlchemy** – ORM + SQLite  
- **Faker** – Data simulation  
- **NLTK** – Text preprocessing  
- **Matplotlib / Seaborn** – Visualization  

---

## 🚀 How to Run

### 1️⃣ Prerequisites
- Python 3.x  
- Jupyter Notebook or JupyterLab  

### 2️⃣ Install dependencies
```bash
pip install pandas sqlalchemy faker nltk matplotlib seaborn
