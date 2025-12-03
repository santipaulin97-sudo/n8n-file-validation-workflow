# ✨ n8n Workflow – File Extraction, Validation & VerdiCode Processing

A powerful and modular **n8n workflow** built to automate **XLSX extraction**, **multi-sheet validation**, and **VerdiCode-based processing**.  
Designed for robust data quality checks and seamless integration with email + Google Sheets actions.

---

## 🎯 Overview

This workflow:

- Downloads and analyzes an XLSX file  
- Validates headers for up to **12 different sheets**  
- Consolidates all validation outputs  
- Triggers automated actions depending on the result  

Ideal for operational teams that need **consistent, repeatable, and auditable** file validation.

---

## 📁 Sheets Processed

The workflow extracts and processes the following tabs:

| Sheet | Description |
|-------|-------------|
| **LABOR** | Employee labor data |
| **INDIRETOS** | Indirect labor |
| **Periodo** | Period metadata |
| **Diaristas** | Daily workers |
| **Hora Extra** | Overtime hours |
| **Absentismo** | Absenteeism |
| **Others** | Misc operational records |
| **Saldo Banco de Horas** | Hour bank balance |
| **Calculadora ABS** | Absence calculator |
| **Allowance** | Allowances |
| **Premiação Presentismo** | Attendance awards |

---

## 🧪 Header Validation Logic

For each sheet, the workflow checks:

- Required columns  
- Missing headers  
- Extra/unexpected headers  

Validation is implemented with **JavaScript Code nodes** to keep logic flexible and maintainable.

Examples:

- LABOR header validation (missing/extra detection)  
- INDIRETOS required headers  
- Placeholder nodes for extended VerdiCode logic  

---

## 🔗 Workflow Orchestration

All validation results are **merged** using an n8n Merge node to determine:

- ✅ If the file is valid  
- ❌ Which errors were found  
- ⚠️ Any warnings (extra headers)

This consolidated output drives the final workflow actions.

---

## 🚀 Final Actions

Depending on the validation status:

### 🔵 If the file is valid  
- Updates a Google Sheet with a new record

### 🔴 If the file contains errors  
- Sends an email with a detailed validation summary  
- Routes execution into VerdiCode-specific logic if needed  

---

## 🛠️ Technologies Used

- **n8n** (workflow automation)
- **JavaScript** (validation logic)
- **Google Sheets API**
- **Gmail API**
- **HTTP Request Integration**

---

## 📦 How to Use

1. Open n8n  
2. Go to **Import Workflow**  
3. Upload `workflow.json`  
4. Configure your credentials:
   - Gmail  
   - Google Sheets  
   - File download URL  
5. Run the workflow  

---

## 👨‍💻 Author

Developed by **Santiago Paulin**  
Data Engineer – Automation, ETL & n8n Workflows

---

## 🌈 Bonus (Optional)

You can add the workflow diagram under a `docs/` folder:

