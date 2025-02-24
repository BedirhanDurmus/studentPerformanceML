# 🎓 Öğrenci Performans Tahmin Sistemi

## 📋 Proje Hakkında
Bu proje, öğrencilerin matematik performansını çeşitli faktörlere dayanarak tahmin eden bir makine öğrenmesi uygulamasıdır. Flask web framework'ü kullanılarak geliştirilmiş ve deployment için hazır hale getirilmiştir.

## 🎯 Özellikler
- Öğrenci demografik bilgilerini analiz eder
- Okuma ve yazma puanlarını değerlendirir
- Test hazırlık durumunu dikkate alır
- Aile eğitim düzeyini göz önünde bulundurur
- Web arayüzü üzerinden kolay kullanım
- Gerçek zamanlı tahmin yapabilme

## 🛠️ Kullanılan Teknolojiler
- Python 3.x
- Flask
- Scikit-learn
- Pandas
- NumPy
- HTML/CSS
- Pickle
- XGBoost
- CatBoost
- RandomForest

## 📁 Proje Yapısı 
studentPerformanceML/
├── artifacts/
├── logs/
├── notebook/
│ └── data/
│ └── stud.csv
├── src/
│ ├── components/
│ │ ├── data_ingestion.py
│ │ ├── data_transformation.py
│ │ └── model_trainer.py
│ ├── pipeline/
│ │ ├── predict_pipeline.py
│ │ └── train_pipeline.py
│ ├── utils.py
│ ├── logger.py
│ └── exception.py
├── templates/
│ ├── home.html
│ └── index.html
├── app.py
└── README.md


## 🔄 Veri İşleme Pipeline'ı
1. **Veri Alımı (Data Ingestion)**
   - Ham verinin okunması
   - Train-test split işlemi
   - Verilerin artifacts klasörüne kaydedilmesi

2. **Veri Dönüşümü (Data Transformation)**
   - Kategorik değişkenlerin one-hot encoding işlemi
   - Sayısal değişkenlerin standardizasyonu
   - Eksik verilerin doldurulması

3. **Model Eğitimi (Model Training)**
   - Çeşitli regresyon modellerinin denenmesi
   - Hyperparameter optimizasyonu
   - En iyi modelin seçilmesi ve kaydedilmesi

4. **Eğitim Pipeline'ı (Train Pipeline)**
   - Veri alımı, dönüşümü ve model eğitimi adımlarını otomatikleştirir
   - En iyi performans gösteren modeli seçer
   - Model performans metriklerini değerlendirir
   - Eğitilmiş modeli ve preprocessor'ı kaydeder

5. **Tahmin Pipeline'ı (Prediction Pipeline)**
   - Web arayüzünden gelen verileri işler
   - Kaydedilmiş preprocessor ile verileri dönüştürür
   - Eğitilmiş model ile tahmin yapar
   - Sonuçları kullanıcıya gösterir

## 💻 Kurulum
1. Repo'yu klonlayın
git clone https://github.com/kullaniciadi/studentPerformanceML.git
bash
pip install -r requirements.txt
bash
python app.py

## 🌐 Kullanım
1. Web tarayıcınızda `http://localhost:5000` adresine gidin
2. Öğrenci bilgilerini girin:
   - Cinsiyet
   - Etnik köken
   - Ebeveyn eğitim düzeyi
   - Öğle yemeği tipi
   - Test hazırlık kursu durumu
   - Okuma puanı
   - Yazma puanı
3. "Predict" butonuna tıklayarak matematik puanı tahminini alın

## 📊 Model Performansı
- Kullanılan modeller:
  - Random Forest
  - XGBoost
  - CatBoost
  - AdaBoost
  - Gradient Boosting
  - Linear Regression
  - Decision Tree

  Model performance report: {'Random Forest': 0.8548407858914417,
   'Decision Tree': 0.742724535050777, 'Gradient Boosting': 0.873444711556977,
   'Linear Regression': 0.8795158595242263, 'XGBRegressor': 0.8492434722253639,
   'CatBoosting Regressor': 0.8613734525258083, 'AdaBoost Regressor': 0.8497782493596903}
  
  Best performing model: Linear Regression
  Best model score: 0.8795158595242263

## 🔍 Özellik Açıklamaları
Modelde kullanılan özellikler:
- **gender**: Öğrencinin cinsiyeti (erkek/kadın)
- **race_ethnicity**: Öğrencinin etnik kökeni (grup A-E)
- **parental_level_of_education**: Ebeveynlerin eğitim seviyesi
- **lunch**: Öğle yemeği tipi (standart/ücretsiz-indirimli)
- **test_preparation_course**: Test hazırlık kursu durumu (tamamlandı/hiç)
- **reading_score**: Okuma puanı (0-100)
- **writing_score**: Yazma puanı (0-100)
- **math_score**: Matematik puanı (hedef değişken)

## 📈 Logging ve İzleme
- Tüm işlemler `logs/` klasöründe tarih-saat formatında kaydedilir
- Her çalıştırma için ayrı log dosyası oluşturulur
- Hata ayıklama ve performans izleme için detaylı logging
- Model eğitim metrikleri ve tahmin sonuçları loglanır

## ⚠️ Hata Yönetimi
- Özel exception handling sistemi
- Detaylı hata mesajları ve stack trace
- Sistemsel ve kullanıcı kaynaklı hataların ayrı yönetimi

## 🔒 Güvenlik Önlemleri
- Input validasyonu
- Veri sanitizasyonu
- Güvenli model deployment
- Hata mesajlarında hassas bilgilerin gizlenmesi

## 🚀 Gelecek Geliştirmeler
- [ ] Docker container desteği
- [ ] CI/CD pipeline entegrasyonu
- [ ] API dokümantasyonu
- [ ] Batch prediction desteği
- [ ] Model versiyonlama sistemi
- [ ] A/B testing altyapısı

## 💡 Öneriler ve İyi Uygulamalar
- Modeli düzenli aralıklarla yeniden eğitin
- Veri setini periyodik olarak güncelleyin
- Model performansını sürekli izleyin
- Yeni özellikler eklerken mevcut pipeline'ı koruyun

## 🤝 Katkıda Bulunma
1. Bu projeyi fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/yeniOzellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeniOzellik`)
5. Pull Request oluşturun

## 📝 Lisans
Bu proje MIT lisansı altında lisanslanmıştır.