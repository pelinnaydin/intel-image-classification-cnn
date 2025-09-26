# intel-image-classification-cnn
Bu repo, Global AI Hub bootcamp projem kapsamında oluşturulmuştur. Amaç, **Intel Image Classification** veri setindeki sahneleri 6 sınıfta (Buildings, Forest, Glacier, Mountain, Sea, Street) CNN tabanlı bir modelle sınıflandırmaktır. Proje **Public** olarak paylaşılmaktadır.

---

## Giriş
Bu çalışmada **Kaggle – Puneet6060 / Intel Image Classification** veri seti kullanılmıştır.  
Modelleme süreci şu adımlardan oluşur:
- Görselleri **224×224** boyutuna getirme, **train/validation/test** ayrımı,
- `tf.data` ile **cache/prefetch** ve veri akışını hızlandırma,
- **Data Augmentation** (RandomFlip, RandomRotation, RandomZoom, RandomContrast),
- **CNN** tabanlı mimari (Conv2D + MaxPooling + Dropout + Dense + Softmax),
- **EarlyStopping** ve **ReduceLROnPlateau** ile eğitim kontrolü,
- Basit bir **hiperparametre araması** (katman/filtre/kernel/dropout/dense/l2/lr/optimizer/batch).

> Projenin teknik anlatımı ve kod açıklamaları, Kaggle notebook içinde **Markdown hücreleriyle** verilmiştir.  
> Yalnızca kod/çıktı değil, **yorum ve açıklamalar** da notebook’ta yer almaktadır.

---

## Metrikler
Çalışmanın temel çıktıları (özet):
- **Validation Accuracy (en iyi)**: **VAL_ACC_YUZDE**  
- **Test Accuracy**: **TEST_ACC_YUZDE**  
- **Accuracy/Loss grafikleri**: epoch bazında eğitim/validasyon eğrileri,
- **Confusion Matrix & Classification Report**: sınıf bazlı performans,
- **Grad-CAM**: modelin karar verirken etkilendiği bölgelerin ısı haritası.

> Yorum: Overfitting gözlendiğinde **Dropout/L2** artırılmış, augmentation aktif tutulmuştur; underfitting durumunda blok/filtre/dense/epoch artırımı denenmiştir.

---

## Ekler
Proje kapsamında ek geliştirmeler için aşağıdaki başlıklar düşünülmüştür:
- **Deployment / UI**: Streamlit tabanlı bir arayüz ile modeli sunma (opsiyonel `UI/` klasörü),
- **İzleme**: TensorBoard veya Weights & Biases ile eğitim takibi,
- **Transfer Learning**: EfficientNet/ResNet vb. ön eğitimli modellerle karşılaştırma.

---

## Sonuç ve Gelecek Çalışmalar
Model; Intel veri setinde 6 sınıf sahne sınıflandırmasını başarıyla gerçekleştirmiştir.  
Gelecekte:
- Daha güçlü **transfer learning** mimarileriyle denemeler,
- **Augmentation** çeşitliliği ve sınıf dengesinin iyileştirilmesi,
- **Keras Tuner / Bayesian Optimization** ile daha sistematik HPO,
- Gerçek-zamanlı veri veya bir **web arayüzü** ile kullanım senaryosu  
planlanmaktadır.

---

## Linkler
- Kaggle Notebook : https://www.kaggle.com/code/pelinaydin/intel-cnn-classification
- Veri seti : https://www.kaggle.com/datasets/puneet6060/intel-image-classification

> Veri seti repoya eklenmemiştir; notebook çıktıları Kaggle üzerinde görülebilir.

---

