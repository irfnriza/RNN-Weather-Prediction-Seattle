# RNN Weather Prediction - Seattle

Project untuk memprediksi cuaca menggunakan Simple RNN (Recurrent Neural Network) berdasarkan dataset cuaca Seattle.

## 📋 Requirements

- Python 3.8 - 3.11
- TensorFlow 2.13+
- NumPy < 2.0 (untuk kompatibilitas dengan TensorFlow)

## 🚀 Instalasi

### 1. Clone atau download project ini

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

**PENTING:** Jika Anda sudah memiliki NumPy 2.x terinstall, jalankan:

```bash
pip uninstall numpy
pip install "numpy<2.0"
```

### 3. Verifikasi instalasi

```bash
python -c "import tensorflow as tf; import numpy as np; print(f'TensorFlow: {tf.__version__}'); print(f'NumPy: {np.__version__}')"
```

Output yang diharapkan:
- TensorFlow: 2.13.x atau lebih tinggi
- NumPy: 1.x.x (harus di bawah versi 2.0)

## 📁 Struktur Project

```
rnn/
├── dataset/
│   └── seattle-weather.csv      # Dataset cuaca Seattle
├── model/                       # Folder untuk menyimpan model terlatih
├── notebook/
│   └── notebook.ipynb          # Jupyter notebook utama
├── requirements.txt            # Dependencies
└── README.md                   # File ini
```

## 🎯 Cara Penggunaan

1. Buka Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Buka file `notebook/notebook.ipynb`

3. Jalankan cell secara berurutan dari atas ke bawah

## 📊 Dataset

Dataset `seattle-weather.csv` berisi data cuaca harian Seattle dengan kolom:
- `date`: Tanggal
- `precipitation`: Curah hujan
- `temp_max`: Temperatur maksimum
- `temp_min`: Temperatur minimum  
- `wind`: Kecepatan angin
- `weather`: Kondisi cuaca (target prediksi)

## 🧠 Model Architecture

Model menggunakan **Simple RNN (Vanilla RNN)** dengan arsitektur:
- SimpleRNN Layer 1: 128 units
- SimpleRNN Layer 2: 64 units
- Dense Layers: 64 → 32 → output
- Dropout: 0.2 - 0.3
- Optimizer: Adam
- Loss: Categorical Crossentropy

## ⚙️ Features

- ✅ **Early Stopping**: Menghentikan training jika tidak ada improvement
- ✅ **Model Checkpoint**: Menyimpan model terbaik
- ✅ **Learning Rate Scheduler**: Mengurangi learning rate saat plateau
- ✅ **Sequence Prediction**: Menggunakan 7 hari data sebelumnya

## 📈 Evaluasi

Model dievaluasi menggunakan:
- Classification Report (Precision, Recall, F1-Score)
- Confusion Matrix
- Accuracy Score
- Visualisasi training history

## ⚠️ Troubleshooting

### ImportError: NumPy compatibility

Jika Anda mendapat error:
```
A module that was compiled using NumPy 1.x cannot be run in NumPy 2.x
```

**Solusi:**
```bash
pip install --upgrade "numpy<2.0"
```

### TensorFlow tidak terinstall dengan benar

```bash
pip uninstall tensorflow
pip install tensorflow
```

## 📝 License

Project ini dibuat untuk tujuan pembelajaran.

## 👨‍💻 Author

Created for weather prediction learning project.
