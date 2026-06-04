# 🎗️ Support Vector Machines (SVM) ile Meme Kanseri Sınıflandırması ve Optimizasyonu

Bu proje, **Bursa Teknik Üniversitesi Bilgisayar Mühendisliği Bölümü - BLM0463 Veri Madenciliğine Giriş** dersi dönem projesi kapsamında geliştirilmiştir. Projede, UCI Machine Learning Repository üzerinde yer alan klasik **Breast Cancer Wisconsin (Diagnostic)** veri seti kullanılarak, hücre çekirdeği özniteliklerinden tümörlerin iyi huylu (*Benign*) veya kötü huylu (*Malignant*) olup olmadığı yüksek başarı oranıyla sınıflandırılmıştır.

## 🚀 Proje Özet Bilgileri
- **Geliştiren:** Mualla Çapar
- **Yöntem:** Destek Vektör Makineleri (Support Vector Machines - SVM)
- **Veri Seti:** [UCI Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)
- **Kullanılan Teknolojiler:** Python, Google Colab, Scikit-Learn, Pandas, NumPy, Seaborn, Matplotlib

---

## 🛠️ Uygulanan Veri Ön İşleme ve Model Adımları

1. **Veri Yükleme:** Veriler UCI veri tabanından `ucimlrepo` API'si kullanılarak canlı olarak çekilmiştir.
2. **Keşifçi Veri Analizi (EDA):** Özniteliklerin dağılımları ve korelasyon matrisleri çıkarılarak verinin geometrik ayrılabilirliği analiz edilmiştir.
3. **Label Encoding:** Kategorik hedef değişken ('M' ve 'B'), makine öğrenmesi modeline uygun şekilde `1` ve `0` değerlerine dönüştürülmüştür.
4. **Veri Bölme (Train-Test Split):** Veri seti adil bir değerlendirme için `%70 Eğitim` ve `%30 Test` olarak ikiye ayrılmıştır.
5. **Standardizasyon (Feature Scaling):** SVM algoritmasının mesafe tabanlı doğası gereği, tüm öznitelikler `StandardScaler` ile normalize edilmiştir.
6. **Hiperparametre Optimizasyonu:** `GridSearchCV` ve **5-Fold Cross Validation** (5 Katmanlı Çapraz Doğrulama) kullanılarak en uygun parametre seti belirlenmiştir.
   - **En İyi Parametreler:** `{'C': 0.1, 'gamma': 1, 'kernel': 'linear'}`

---

## 📊 Deneysel Sonuçlar ve Başarı Metrikleri

Geliştirilen optimize Doğrusal SVM modeli, daha önce hiç görmediği test seti üzerinde sınanmış ve aşağıdaki yüksek başarı metriklerine ulaşmıştır:

| Performans Ölçütü | Başarı Skoru |
| :--- | :--- |
| **Doğruluk (Accuracy)** | % 98.25 |
| **Duyarlılık (Sensitivity / Recall)** | % 96.83 |
| **Özgünlük (Specificity)** | % 99.07 |
| **Keskinlik (Precision)** | % 98.39 |
| **F-Ölçüsü (F1-Measure)** | % 97.60 |
| **ROC AUC Skoru** | 0.9942 |

### Hata Matrisi (Confusion Matrix) Özeti:
- **Toplam Test Örneği:** 171 hasta
- **Doğru Teşhis Edilen Sağlıklı (TN):** 107
- **Doğru Teşhis Edilen Kanser (TP):** 61
- **Kritik Hata (False Negative - FN):** Sadece 2 (Kanserli olduğu halde gözden kaçan)

---

## 📑 Akademik Literatür Karşılaştırması

Projede elde edilen optimizasyon başarısı, literatürde aynı veri setiyle yapılmış temel çalışmalarla kıyaslanmıştır:

| Çalışma / Kaynak | Kullanılan Algoritma | Doğruluk (Accuracy) |
| :--- | :--- | :--- |
| Street ve ark. (1993) - Orijinal UCI Makalesi | MSM-T (Doğrusal Ağaç) | % 97.30 |
| Chaurasia & Pal (2020) | Standart SVM | % 96.80 |
| Amrane ve ark. (2018) | Linear SVM | % 97.38 |
| **Bu Proje (Mualla Çapar)** | **Optimized Linear SVM (C=0.1)** | **% 98.25** |

---

## 📂 Proje Yapısı

```text
├── BLM463_Proje_Notebook.ipynb   # Veri analizi, model eğitimi ve test kodları (Colab)
├── README.md                     # Proje tanıtım ve dokümantasyon dosyası
└── BLM463_Proje_MuallaCapar_OgrenciNo.pdf # Detaylı akademik proje raporu
