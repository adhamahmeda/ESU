# 📘 Smart Utility AI Assistant (ElSewedy Utilities Support)

## 🧩 Overview
This project provides a **web-based Smart Utility Management and AI Assistant System** built using **React (via Babel standalone), TailwindCSS, jsPDF, html2canvas, and Express.js**.  
It includes two versions:
1. **`index.html`** – *ElSewedy Utilities Support (Final Version)*  
2. **`index2.html`** – *Smart Utility AI Assistant (Advanced Version)*  

Both simulate a bilingual (Arabic/English) utility management dashboard that helps users view consumption data, download invoices, and interact with an AI assistant for customer support, billing, policies, and complaints.

---

## ⚙️ Features
- 🧠 **AI Chat Assistant (RAGAgent)**  
  Responds in both English and Arabic to queries about:
  - Bills & consumption  
  - Payments & policies  
  - Complaint handling & support  

- 💡 **Simulated Database System**  
  Stores users, consumption, meters, and payment records in-memory (`index.html`) or localStorage (`index2.html`).

- 📊 **Interactive Dashboard**  
  Displays usage and cost summaries for Gas, Electricity, and Water utilities.

- 💬 **Dual Language Support**  
  Fully bilingual UI and chatbot (English / Arabic with RTL support and Amiri font).

- 💾 **PDF & Excel Integration**
  - Generate reports (`arabicpdf.html`)  
  - Save assignment/invoice data via backend `/save-assignments` endpoint.  

- 🌐 **Backend API (Express.js)**  
  A lightweight server (`server-8000.js`) for serving files and saving Excel reports.

---

## 🗂️ Project Structure
```
project-root/
├── index.html              # ElSewedy Utilities Support app
├── index2.html             # Smart Utility AI Assistant (Advanced version)
├── arabicpdf.html          # Arabic-styled utility report (PDF template)
├── assignments.xlsx        # Excel data (assignments)
├── invoices.xlsx           # Excel data (invoices)
├── package.json            # Node dependencies (Express)
├── package-lock.json
├── server-8000.js          # Express server (port 8000)
```

---

## 🖥️ Installation & Setup

### 1. Prerequisites
- Node.js **v18+**
- npm (included with Node)

### 2. Install dependencies
```bash
npm install
```

### 3. Start the server
```bash
node server-8000.js
```

By default, it runs on:
```
http://localhost:8000
```

### 4. Open Frontend
- Open **`index.html`** or **`index2.html`** in your browser directly, or  
- Serve them from the same directory as the backend (they’ll be accessible via the local server).

---

## 💬 Usage Instructions
1. Launch the app (`index.html` or `index2.html`).
2. Log in with demo credentials:
   ```
   Username: user001
   Password: 123  (or password123 for index2.html)
   ```
3. Navigate through:
   - **Dashboard** → View balance and costs  
   - **Consumption Summary** → Detailed usage data  
   - **AI Assistant** → Ask about bills, payments, or policies  
4. Generate or download PDFs (auto-generated via `html2canvas` + `jsPDF`).

---

## 🧠 Example AI Queries
| Language | Example Query | Expected Response |
|-----------|----------------|------------------|
| English | “Show me my unpaid bills.” | Lists all unpaid invoices and total amount |
| Arabic | “ما هي سياسة الكهرباء؟” | Explains tiered pricing and charges |
| English | “File a complaint about my water bill.” | Generates complaint reference number |

---

## 📡 API Endpoints
### `POST /save-assignments`
Saves base64-encoded Excel data to `assignments.xlsx`.

**Request:**
```json
{
  "data": "data:application/vnd.openxmlformats-officedocument.spreadsheetml.sheet;base64,AAAA..."
}
```

**Response:**
```json
{ "status": "ok" }
```

---

## 🧾 License
Licensed under the **ISC License**.

---

## 👤 Author
Developed by **Adham Ahmed**  
Computer Science & AI, UWE Bristol  
