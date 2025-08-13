# **CAPSTONE MODUL 3**
## **Muhammad Alif Hidayah - JCDS 011**

# 🚗 PT. AutoPredict Arabia — Machine Learning for Used Car Price Prediction

Proyek ini bertujuan membangun **sistem rekomendasi harga mobil bekas** berbasis Machine Learning untuk pasar Arab Saudi. Sistem ini memprediksi harga jual optimal berdasarkan data kendaraan, kondisi, dan tren pasar, dengan tujuan meningkatkan akurasi valuasi, mempercepat proses penjualan, dan mengoptimalkan pendapatan.

---

## 📌 Latar Belakang
Pasar mobil bekas di Arab Saudi memiliki potensi besar dengan pertumbuhan permintaan yang signifikan. Namun, penentuan harga masih banyak dilakukan secara manual, yang memicu masalah:
- Perbedaan estimasi harga hingga ±20%
- Risiko **overpricing** (penjualan lambat) dan **underpricing** (margin rendah)
- Proses valuasi yang memakan waktu

---

## 🎯 Tujuan Proyek
- Mengembangkan **pricing copilot** berbasis Machine Learning
- Mengurangi error penilaian harga hingga 30–40% dibanding metode konvensional
- Menyediakan harga rekomendasi dan **rentang aman (P10–P90)** untuk negosiasi
- Memberikan insight portofolio stok berdasarkan tren harga & permintaan

---

## 📊 Dataset
- **Total data**: 5.624 entri
- **Fitur utama**:
  - Tahun, Merek, Model, Varian
  - Mileage, Engine Size, Transmission, Origin
  - Region/Lokasi, Harga historis
- **Sumber**: Data marketplace mobil bekas di Arab Saudi
- **Distribusi harga**: Terkonsentrasi di 50k–150k SAR, sweet spot 100k–250k SAR

---

## ⚙️ Metodologi
Metode pengembangan mengikuti **CRISP-DM**:
1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment

**Preprocessing:**
- Outlier removal (IQR method)
- Handling missing values
- Encoding kategori (BinaryEncoder + OneHotEncoder)
- Scaling numerik (RobustScaler)
- Train-test split 80:20 dengan stratifikasi harga

---

## 🤖 Model yang Diuji
- **Baseline:** Linear Regression
- **Candidate Models:** Decision Tree, Random Forest, XGBoost, CatBoost
- **Best Model:** CatBoost (tuned)

**Alasan pemilihan CatBoost:**
- Performa terbaik di semua metrik
- MAPE rendah di segmen utama
- Built-in handling untuk fitur kategori & missing values

---

## 📈 Hasil Evaluasi
**Cross-validation (mean):**
- RMSE ≈ 27.282
- MAE ≈ 13.794
- MAPE ≈ 19,5%

**Holdout (tuned CatBoost):**
- RMSE: 23.627
- MAE: 14.008
- MAPE: 24,3%

**Segmen Terbaik:** 100k–250k SAR (MAPE ~13–15%)  
**Segmen Risiko Tinggi:** <20k SAR & >350k SAR (data tipis & variasi besar)

---

## 💡 Business Impact
- **Uplift pendapatan:** ~+1,35% (+1,15 juta SAR) jika harga rekomendasi digunakan penuh
- **Efisiensi waktu:** Penilaian harga instan melalui API
- **Pengurangan risiko:** Guard-rails ±5–8% dan rentang harga P10–P90
- **Optimalisasi stok:** Fokus pada segmen mid-market yang likuid

---

## 🛠️ Instalasi & Penggunaan
```bash
# Clone repository
git clone https://github.com/username/AutoPredict-Arabia.git

# Masuk ke folder proyek
cd AutoPredict-Arabia

# Install dependencies
pip install -r requirements.txt

# Jalankan notebook untuk training
jupyter notebook "Final Capstone 3.ipynb"
