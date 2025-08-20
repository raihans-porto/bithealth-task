# 🏥 Medical Department Recommender

## 📖 Deskripsi
Aplikasi ini merupakan implementasi **mini project End-to-End** untuk sistem triase rumah sakit.  

Pasien dapat memasukkan informasi dasar (*gender*, *usia*, *gejala*) dan sistem akan merekomendasikan **departemen medis** yang sesuai menggunakan **Google Gemini API** melalui **LangChain**.  

🎯 **Tujuan sistem**  
- Mempercepat proses triase pasien  
- Mengurangi human error pada rujukan awal  
- Meningkatkan pengalaman pasien dan efisiensi alur rumah sakit  

---

## 📂 Struktur Project
```bash
.
├── app.py              # Main FastAPI app
├── requirements.txt    # Dependencies
├── .env                # API Key
└── templates/
    └── index.html      # Frontend (form input pasien)
```

---

## ⚙️ Instalasi & Menjalankan

### 1. Download File
Download semua file yang sudah disediakan dari Google Drive.

https://drive.google.com/file/d/1InSbMpLQSlAhbK-uqNvnt0kL5SGGh1NA/view?usp=drive_link

### 2. Buat virtual environment (opsional, tapi direkomendasikan):
```bash
python -m venv env_ai
```

- Windows
```powershell
env_ai\Scripts\activate   
```

- Linux/Mac
```bash
source env_ai/bin/activate   
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```
### 4. Set API Key Google Gemini sebagai LLM
- Buat file .env di folder project dengan isi:
```env
GOOGLE_API_KEY=your_api_key_here
```

### 5. Jalankan aplikasi
```bash
uvicorn app:app --reload
```

## 📌 Cara Penggunaan

### 🔹 A. Versi API (JSON)
- Gunakan curl atau Postman:

1. Windows
```power shell
curl -Method POST "http://127.0.0.1:8000/recommend" `
-Headers @{ "Content-Type" = "application/json" } `
-Body '{"gender":"female","age":62,"symptoms":["pusing","mual","sulit berjalan"]}'
```

2. Linux/Mac
```bash
curl -X POST "http://127.0.0.1:8000/recommend" \
-H "Content-Type: application/json" \
-d '{"gender":"female","age":62,"symptoms":["pusing","mual","sulit berjalan"]}'
```

- Output yang akan keluar nantinya:

{
  "recommended_department": "Neurology"
}

### 🔹 B. Versi Web (Form HTML)
- Jika ingin mencoba langsung lewat browser:
1. Buka http://127.0.0.1:8000
2. Isi form:
- Gender    : female
- Age       : 62
- Symptoms  : pusing, mual, sulit berjalan
3. Klik Predict
4. Hasil rekomendasi departemen akan muncul di bawah form.

- Contoh tampilan:
<img width="1919" height="857" alt="image" src="https://github.com/user-attachments/assets/7b4c3504-1756-430e-9e2d-347d5552f9d7" />

<img width="1918" height="633" alt="image" src="https://github.com/user-attachments/assets/2b6ed875-9101-4584-a7cd-c297141b90f7" />


