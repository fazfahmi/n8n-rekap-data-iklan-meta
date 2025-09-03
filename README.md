# 📊 n8n Workflow – Kiyoko Rekap Data

## 📝 Deskripsi
Workflow ini dibuat menggunakan **n8n** untuk mengotomatisasi proses **penarikan data iklan dari Meta (Facebook Ads)** melalui **Facebook Graph API**, kemudian menyimpannya ke **Google Sheets**.  
Workflow berjalan secara terjadwal sehingga tim marketing selalu memiliki data performa iklan terbaru tanpa harus melakukan input manual.

---

## ⚙️ Alur Workflow
1. **Schedule Trigger**  
   - Workflow dijalankan otomatis setiap hari pukul 08:00 WIB.  

2. **Facebook Graph API Nodes**  
   - Mengambil data kampanye iklan (`campaign_name`, `spend`, `conversion`, dsb).  
   - Beberapa node digunakan untuk berbagai akun/ID kampanye.  

3. **Split Out Node**  
   - Memecah array `data` dari Graph API agar setiap record bisa diproses per baris.  

4. **If Node (Conditional)**  
   - Menyaring campaign tertentu sesuai nama/ID.  

5. **Google Sheets Nodes**  
   - Menyimpan data hasil extract ke beberapa sheet berbeda (contoh: **FB-Shopee**, **FB-CPAS Raw**, **FB-CTWA Raw**).  
   - Menggunakan `Unique ID` atau `Tanggal` sebagai kunci update agar tidak duplikat.  

---

## 🖼️ Contoh Workflow
*(Tambahkan screenshot editor n8n di sini, misalnya `workflow-editor.png`)*  

---

## 📂 Struktur Repository
```bash
📁 n8n-kiyoko-rekap-data
 ┣ 📄 Kiyoko Rekap Data.json   # Export workflow dari n8n (dummy credential)
 ┣ 📄 README.md                # Dokumentasi workflow
 ┗ 📂 screenshots              # Screenshot editor n8n & contoh output
