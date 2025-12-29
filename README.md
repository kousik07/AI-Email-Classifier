# 📧 AI-Powered Email Order Processing & Inquiry Management System

This project implements an **AI-driven system** that automatically processes customer emails for a fashion retail store using **Large Language Models (LLMs)** and **Retrieval-Augmented Generation (RAG)**.

The system intelligently classifies emails, processes product orders based on stock availability, answers product inquiries using a scalable retrieval approach, and generates professional customer-ready responses. All results are exported into a structured Excel file.

---

## 🚀 Key Capabilities

- ✅ Email intent classification (Order Request vs Product Inquiry)
- ✅ LLM-based extraction of products and quantities
- ✅ Real-time stock validation and inventory updates
- ✅ RAG-based product inquiry handling using FAISS
- ✅ Professional email response generation
- ✅ Scalable design suitable for large product catalogs (100k+ items)
- ✅ Final output exported to a single Excel file with multiple sheets

---

## 🧠 Architecture Overview


---

## 🛠️ Tech Stack

- **Python**
- **OpenAI GPT-5-nano** – lightweight, cost-efficient LLM
- **LangChain** – LLM orchestration
- **FAISS** – vector similarity search
- **Pandas** – data processing
- **OpenPyXL** – Excel export

---

## 📂 Input Data

### Product Catalog
Contains:
- Product ID
- Name
- Category
- Description
- Season
- Stock quantity

### Customer Emails
Contains:
- Email ID
- Subject
- Message body

---

## 🔍 Core Functions Explained

### 1️⃣ `classify_email(email_text)`

**Purpose:**  
Classifies each incoming email as either:
- `order request`
- `product inquiry`

**How it works:**
- Uses GPT-5-nano with a strict prompt
- Returns a single label only (no extra text)
- Avoids rule-based or keyword logic

**Why it matters:**  
Accurate intent detection is critical for routing emails to the correct processing flow.

---

### 2️⃣ `extract_order_items(email_text)`

**Purpose:**  
Extracts ordered products and quantities from unstructured email text.

**Output Example:**
```json
[
  { "product_name": "summer dress", "quantity": 2 }
]
