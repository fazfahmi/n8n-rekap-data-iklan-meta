# 📊 n8n Workflow – Kiyoko Data Recap

## 📝 Description
This workflow was built using **n8n** to automate the process of **retrieving advertising data from Meta (Facebook Ads)** via the **Facebook Graph API** and storing it in **Google Sheets**.  
The workflow runs on a daily schedule so that the marketing team always has up-to-date performance data without manual input.

---

## ⚙️ Workflow Steps
1. **Schedule Trigger**  
   - The workflow runs automatically every day at 08:00 (GMT+7).  

2. **Facebook Graph API Nodes**  
   - Pulls campaign data (`campaign_name`, `spend`, `conversion`, etc.).  
   - Multiple nodes are used for different accounts or campaign IDs.  

3. **Split Out Node**  
   - Splits the `data` array from the Graph API into individual records for processing.  

4. **If Node (Conditional)**  
   - Filters specific campaigns by name or ID.  

5. **Google Sheets Nodes**  
   - Appends or updates the extracted data into multiple Google Sheets (e.g., **FB-Shopee**, **FB-CPAS Raw**, **FB-CTWA Raw**).  
   - Uses `Unique ID` or `Date` as the key to prevent duplicates.  

---

## 🖼️ Workflow Example
<img width="1164" height="804" alt="image" src="https://github.com/user-attachments/assets/6d8a3cdc-88fe-4501-80ec-6811521fb65e" />


---

## 📂 Repository Structure
```bash
📁 n8n-kiyoko-data-recap
 ┣ 📄 Kiyoko Data Recap.json   # Exported workflow from n8n (with dummy credentials)
 ┣ 📄 README.md                # Workflow documentation
 ┗ 📂 screenshots              # n8n editor & output examples
