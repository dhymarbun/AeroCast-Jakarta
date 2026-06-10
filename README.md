# 🌫️ AeroCast Jakarta

<div align="center">

![AeroCast Jakarta](https://raw.githubusercontent.com/raaihansvg/AeroCast-Jakarta/main/bundaran-hi-graded.jpg)

**Real-time Jakarta Air Quality Monitoring & ISPU Prediction**

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.x-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![XGBoost](https://img.shields.io/badge/XGBoost-Model-FF6600?style=flat-square)](https://xgboost.readthedocs.io)
[![WAQI API](https://img.shields.io/badge/WAQI-API-4CAF50?style=flat-square)](https://waqi.info)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

</div>

---

## 📌 Tentang Proyek

**AeroCast Jakarta** adalah aplikasi web monitoring kualitas udara real-time untuk DKI Jakarta. Sistem ini memprediksi kategori **ISPU (Indeks Standar Pencemar Udara)** menggunakan model machine learning XGBoost yang dilatih dari data sensor 5 stasiun pemantau resmi DKI Jakarta, dengan data diambil langsung melalui WAQI API.

> Dikembangkan sebagai bagian dari kompetisi **AI For Real Impact 2026**.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|-------|-----------|
| 🔴 **Real-time Monitoring** | Data langsung dari 5 stasiun pemantau DKI Jakarta via WAQI API |
| 🤖 **Prediksi ISPU** | Klasifikasi kualitas udara menggunakan model XGBoost (21 fitur) |
| 📊 **4 Kategori ISPU** | Baik · Sedang · Tidak Sehat · Sangat Tidak Sehat |
| 🗺️ **5 Stasiun** | Bundaran HI · Kelapa Gading · Jagakarsa · Lubang Buaya · Kebon Jeruk |
| 🎮 **Mode Simulasi** | Uji prediksi dengan input parameter manual |
| 📱 **Responsive UI** | Desain modern berbasis dark editorial aesthetic |

---

## 🏗️ Arsitektur

```
AeroCast-Jakarta/
├── index.html              # Frontend utama
├── bundaran-hi-graded.jpg  # Hero image
├── src/
│   ├── css/
│   │   └── style.css       # Stylesheet
│   └── js/
│       └── app.js          # Frontend logic
└── backend/
    ├── app.py              # Flask REST API
    ├── model/              # XGBoost model (.pkl)
    └── requirements.txt    # Python dependencies
```

### Alur Data

```
WAQI API → Flask Backend → XGBoost Model → Prediksi ISPU → Frontend
```

---

## 🛠️ Tech Stack

**Frontend**
- HTML5, CSS3 (Vanilla)
- JavaScript (ES6+)
- Canvas API (animasi radar)

**Backend**
- Python 3.12
- Flask (REST API)
- XGBoost (model prediksi)
- Pandas, NumPy, Scikit-learn

**Data Source**
- [WAQI API](https://waqi.info) — World Air Quality Index

---

## 🚀 Cara Menjalankan

### Prerequisites
- Python 3.10+
- pip
- WAQI API Token (daftar gratis di [aqicn.org/data-platform/token](https://aqicn.org/data-platform/token))

### 1. Clone Repository

```bash
git clone https://github.com/raaihansvg/AeroCast-Jakarta.git
cd AeroCast-Jakarta
```

### 2. Setup Backend

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Konfigurasi Environment

Buat file `.env` di folder `backend/`:

```env
WAQI_TOKEN=your_waqi_api_token_here
```

### 4. Jalankan Backend

```bash
python app.py
# Backend berjalan di http://localhost:5001
```

### 5. Jalankan Frontend

Buka `index.html` langsung di browser, atau gunakan live server:

```bash
# Menggunakan Python HTTP server
python -m http.server 8080
# Buka http://localhost:8080
```

---

## 📡 API Endpoints

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| `GET` | `/api/realtime?station=DKI1` | Data real-time + prediksi ISPU |
| `POST` | `/api/predict` | Prediksi dari input manual |
| `GET` | `/api/ping` | Health check backend |

---

## 🗺️ Stasiun Pemantau

| ID | Lokasi | Wilayah |
|----|--------|---------|
| DKI1 | Bundaran HI | Jakarta Pusat |
| DKI2 | Kelapa Gading | Jakarta Utara |
| DKI3 | Jagakarsa | Jakarta Selatan |
| DKI4 | Lubang Buaya | Jakarta Timur |
| DKI5 | Kebon Jeruk | Jakarta Barat |

---

## 📊 Model Machine Learning

- **Algoritma:** XGBoost Classifier
- **Fitur:** 21 parameter (PM2.5, PM10, SO₂, CO, O₃, NO₂, suhu, kelembaban, kecepatan angin, dll)
- **Target:** 4 kategori ISPU (0=Baik, 1=Sedang, 2=Tidak Sehat, 3=Sangat Tidak Sehat)
- **Data Training:** Historical ISPU DKI Jakarta

---

## 📄 Lisensi

Didistribusikan di bawah [MIT License](LICENSE).

---

<div align="center">
  <sub>Built with ❤️ for Jakarta · <a href="https://github.com/raaihansvg">raaihansvg</a></sub>
</div>
