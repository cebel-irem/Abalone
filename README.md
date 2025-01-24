# Abalone Yaş Tahmini

Bu proje, **Abalone Veri Seti** kullanılarak deniz kulaklarının (abalone) yaşını tahmin etmeyi amaçlamaktadır. Projede, farklı makine öğrenimi algoritmaları uygulanarak tahmin modelleri geliştirilmiş ve bu modellerin performansları karşılaştırılmıştır.

## 📋 Veri Seti Hakkında

Abalone veri seti, deniz kulaklarının fiziksel özelliklerini ve bu özelliklere dayanarak yaşlarının tahmin edilmesini sağlayan bir veri setidir. Veri setinde toplamda **8 bağımsız değişken** ve **1 bağımlı değişken (yaş)** bulunmaktadır. Fiziksel ölçümler arasında uzunluk, çap, yükseklik, ağırlık gibi özellikler yer almaktadır.

- **Bağımsız Değişkenler (X):**
  - Cinsiyet (Sex)
  - Uzunluk (Length)
  - Çap (Diameter)
  - Yükseklik (Height)
  - Tüm Ağırlık (WholeWeight)
  - Kabuk Ağırlığı (ShuckedWeight)
  - İç Organ Ağırlığı (VisceraWeight)
  - Kabuk Ağırlığı (ShellWeight)
- **Bağımlı Değişken (Y):**
  - Halkalar (Rings) (yaş tahmini için kullanılır)

**Veri Setine Ulaşım:**  
[Abalone Veri Seti - UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/1/abalone)

---

## 🚀 Kullanılan Algoritmalar

Proje kapsamında aşağıdaki algoritmalar uygulanmıştır:

1. **Destek Vektör Regresyonu (SVR)**:
   - Özellikle doğrusal olmayan veri setlerinde başarılı tahmin yapabilen bir algoritmadır. Projede SVR modeli kullanılarak halkaların (Rings) tahmini gerçekleştirilmiştir.
   - Kullanılan Çekirdek: `RBF (Radial Basis Function)`

2. **K-En Yakın Komşu Regresyonu (KNNR)**:
   - Her bir tahmini yapmak için veri noktalarının en yakın komşularını kullanır. Basit ama etkili bir algoritmadır.
   - Komşu Sayısı: `k=5`

3. **Karar Ağacı Regresyonu (DTR)**:
   - Veri setini dallara bölerek tahminler yapan karar tabanlı bir modeldir. Projede derinlik ve diğer hiperparametreler optimize edilmiştir.

---

## ⚙️ Kurulum ve Çalıştırma

Projeyi çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

### 1. Gerekli Kütüphanelerin Yüklenmesi
```bash
pip install pandas numpy scikit-learn matplotlib
```

### 2. Kodun Çalıştırılması
Python dosyasını çalıştırarak modellerin eğitimi ve test sonuçlarını görebilirsiniz:
```bash
python abalone_model.py
```

---

## 📊 Sonuçlar ve Performans Karşılaştırması

Her modelin performansı, aşağıdaki değerlendirme metrikleri kullanılarak ölçülmüştür:
- **MAE (Mean Absolute Error):** Ortalama mutlak hata.
- **MSE (Mean Squared Error):** Ortalama kare hata.
- **R² (R-Squared):** Belirleme katsayısı.

### Performans Özeti:
| Model   | Eğitim MAE | Test MAE | Eğitim R² | Test R² |
|---------|------------|----------|-----------|---------|
| **SVR** | 0.087      | 0.093    | 0.988     | 0.992   |
| **KNNR**| 0.160      | 0.198    | 0.990     | 0.986   |
| **DTR** | 0.475      | 0.459    | 0.964     | 0.970   |

- **SVR**, düşük MAE ve yüksek R² skorları ile en iyi performansı sergilemiştir.
- **KNNR**, genel performansı iyi olsa da SVR kadar başarılı değildir.
- **DTR**, tahmin edilebilirliği yüksek bir modeldir, ancak diğer iki modele kıyasla biraz daha az hassastır.

---

## 📈 Görselleştirme

Modellerin tahmin performanslarını karşılaştırmak için aşağıdaki görseller üretilmiştir:

- **Gerçek ve Tahmini Değerlerin Dağılımı**:
  - Her model için scatter plot ile gerçek ve tahmini değerlerin karşılaştırması.
- **MAE ve R² Karşılaştırması**:
  - Bar grafikleri ile eğitim ve test setindeki performans karşılaştırmaları.

---

## 🛠️ Gelecek Çalışmalar

1. Daha karmaşık modeller (ör. XGBoost, Random Forest) ile performans artırılabilir.
2. Veri setine veri artırımı teknikleri uygulanabilir.
3. Özellik mühendisliği ile bağımsız değişkenlerin etkileri optimize edilebilir.
