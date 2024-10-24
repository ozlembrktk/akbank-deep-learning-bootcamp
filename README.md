# akbank-deep-learning-bootcamp
Bu proje Global AI Hub Akbank Derin Öğrenme Bootcamp'i için hazırlanmıştır. 
Proje Kaggle'daki A Large-Scale Dataset for Fish Segmentation and Classification veri setini kullanarak kaggle üzerinde geliştirilmiştir.

KAGGLE LINK: https://www.kaggle.com/code/ozlemambarkutuk/deep-learning-bootcamp-fish-classificaiton


Not: /opt/conda/lib/python3.10/site-packages/keras/src/trainers/data_adapters/py_dataset_adapter.py:121: UserWarning: Your `PyDataset` class should call `super().__init__(**kwargs)` in its constructor. `**kwargs` can include `workers`, `use_multiprocessing`, `max_queue_size`. Do not pass these arguments to `fit()`, as they will be ignored.
  self._warn_if_super_not_called()
  uyarısı alınmaktadır. Nedenini bilmediğim bu uyarıyı nasıl çözeceğim konusunda yardımcı olursanız sevinirim.

Proje Akış Planı

Veri Hazırlığı:

Veri seti, her biri belirli bir balık sınıfını temsil eden farklı klasörlere düzenlenmiştir.
Görseller, 590x445 boyutlarına küçültülmüş ve normalize edilmiştir (piksel değerleri 0 ile 1 arasında ölçeklendirilmiştir).


Model Mimarisi:

TensorFlow/Keras kullanılarak bir Evrişimsel Sinir Ağı (CNN) inşa edilmiştir.
Model, birkaç evrişim ve maksimum havuzlama (max-pooling) katmanının yanı sıra tam bağlı katmanlardan oluşmaktadır.
Çıkış katmanı, 9 balık türü için çok sınıflı sınıflandırma amacıyla softmax aktivasyon fonksiyonu kullanmaktadır.

Model Derleme ve Eğitim:

Model, Adam optimizasyon algoritması ve kategorik çapraz entropi (categorical cross-entropy) kayıp fonksiyonu ile derlenmiştir.
Aşırı öğrenmeyi önlemek için doğrulama kaybı izlenerek erken durdurma (early stopping) kullanılmıştır.

Model Değerlendirmesi:

Modelin performansı, doğrulama ve test setleri üzerindeki doğruluk (accuracy) ve kayıp (loss) değerleri ile değerlendirilmiştir.
Sınıflandırma performansını görselleştirmek için bir karmaşıklık matrisi (confusion matrix) oluşturulmuştur.
