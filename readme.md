# Android Malware Analizi

Bu proje, Android malware tespiti üzerine odaklanmaktadır. İki farklı veri seti (CIC-AndMal2017 ve CICMalDroid2020) ile çeşitli makine öğrenmesi algoritmaları karşılaştırılmış ve analiz yapılmıştır.

## 📊 Genel Bakış

### Kullanılan Veri Setleri

Bu projede kullanılan veri setleri aşağıdaki kaynaklardan alınmıştır:

1. **CIC-AndMal2017**: Android uygulamalarından elde edilen ağ trafiği verileri
   - **Kaynak**: [Canadian Institute for Cybersecurity. (2017).](https://www.unb.ca/cic/datasets/andmal2017.html)
   - **Kaggle Kaynağı**: [Subhajournal. (2022).](https://www.kaggle.com/datasets/subhajournal/android-malware-detection)

     _(Bu veri seti de CIC-AndMal2017 verilerini kullanmaktadır)_

2. **CICMalDroid2020**: Android sistem ve binder çağrıları verileri
   - **Kaynak**: [Canadian Institute for Cybersecurity. (2020).](https://www.unb.ca/cic/datasets/maldroid-2020.html)

### Ana Hedefler

- Android malware tespiti için farklı makine öğrenmesi modelleri geliştirmek ve performanslarını karşılaştırmak.
- Binary ve multi-class classification yaklaşımlarını değerlendirmek.
- Veri setlerindeki örüntüleri ve anormallikleri görselleştirerek daha detaylı analizler yapmak.

## 🛠️ Kullanılan Teknolojiler

### Python Kütüphaneleri

- **Pandas**: Veri manipülasyonu ve analizi
- **NumPy**: Sayısal hesaplamalar
- **Scikit-learn**: Makine öğrenmesi algoritmaları
- **XGBoost**: Gradient boosting algoritması
- **LightGBM**: Hafif gradient boosting
- **Matplotlib & Seaborn**: Veri görselleştirme

### Makine Öğrenmesi Algoritmaları

- Decision Tree Classifier
- Random Forest Classifier
- XGBoost Classifier
- LightGBM Classifier
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Bagging Classifier

## 🚀 Nasıl Çalıştırılır

### Gereksinimler

```bash
pip install pandas numpy scikit-learn xgboost lightgbm matplotlib seaborn
```

### Jupyter Notebook Çalıştırma

1. Proje dizinine gidin
2. Jupyter Notebook'u başlatın:
   ```bash
   jupyter notebook big-data.ipynb
   ```
3. Notebook'u sırayla çalıştırın

## 📈 Ana Bulgular

### 🔍 En İyi Performansı Gösteren Modeller

- **CIC-AndMal2017** veri setinde:
  - **Decision Tree + Bagging Classifier** en iyi sonuçları vermiştir.

- **CICMalDroid2020** veri setinde:
  - **XGBoost** algoritması, optimize edilmiş hiperparametrelerle en iyi sonuçları vermiştir.

### ⭐ Önemli Özellikler

- **CIC-AndMal2017** veri seti:
  - `Source Port`: Ağ bağlantısının başladığı kaynağın port numarasını belirtir. Bazı portlar göze çarpıyor.
  - `Flow Bytes/s`: Akış başına saniyede iletilen bayt miktarıdır. Özellikle SMS Malware sınıfında göze çarpıyor.

- **CICMalDroid2020** veri seti:
  - `ACCESS_PERSONAL_INFO_____`: Cihazdaki kişisel bilgilere erişim davranışını gösterir. En çok malware türlerinde yüksek seviyede görülüyor.
  - `getDisplayInfo`: Ekran bilgisi gibi detayları alır. En çok Adware sınıfında görülüyor.
  - `access`: Dosyalara erişim izni sorgular. En çok Banking Malware sınıfında görülüyor.


## 🎯 Katkılar ve Gelecek Çalışmalar

### Katkılar

Bu çalışma, Android tabanlı malware tespitinde ağ trafiği, sistem çağrıları ve binder çağrıları gibi davranışsal verilerle makine öğrenmesi yöntemlerinin etkinliğini ortaya koymuştur. Ağaç tabanlı modellerin başarısı gösterilerek yöntem seçimine katkı sağlanmış, davranışsal analizlerin imza tabanlı yöntemlere alternatif olabileceği vurgulanmıştır.

### Gelecek Çalışmalar

- Derin öğrenme algoritmaları ile performans karşılaştırmaları yapılabilir.
- Bellek dökümü gibi farklı veri türleri entegre edilebilir.
- Gerçek zamanlı tespit sistemleri geliştirilebilir.
- Statik ve dinamik analiz yöntemleri birleştirilebilir.
- Farklı Android sürümleri ve cihazlarda model tutarlılığı test edilebilir.
- Tür bazlı tespit sistemleri için özelleştirilmiş modeller geliştirilebilir.
