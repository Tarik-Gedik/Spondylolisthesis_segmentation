
---
# Omurga Görüntüleri Üzerinde Segmentasyon ve Görüntü İşleme

Bu proje, omurga görüntüleri üzerinde segmentasyon gerçekleştirmek ve görüntü işleme tekniklerini çok seviyeli olarak değerlendirmek amacıyla geliştirilmiştir. DeepLabV3+ segmentasyon modeli ile birlikte farklı ön işleme, kenar analizi ve çok ölçekli (pyramid) yapıların etkisi incelenmektedir.

---

## ⚙️ Kullanılan Teknolojiler

- Python 3.x
- PyTorch
- torchvision
- OpenCV
- scikit-image
- NumPy
- Matplotlib

---

## 🚀 Notebook Açıklamaları

### ✅ `yapayZeka.ipynb`  
- DeepLabv3 + MobileNetV3 modeli ile omurga görüntüleri segmentasyonu yapılır.  
- FP16 (yarı hassasiyetli) eğitim desteklidir.  
- IoU metriği ile başarı analizi gerçekleştirilir.  

### ✅ `Onisleme.ipynb`  
- Görseller normalize edilir ve çeşitli filtreleme teknikleriyle işlenir.  
- 7 farklı pipeline tanımlanır.  
- Shannon entropisi ile en bilgi taşıyan görsel işlem adımı seçilir.  

### ✅ `KenarDesenKodla.ipynb`  
- Etiketlerden kenar çizgileri çıkarılır.  
- Bu kenarlar üzerinden:
  - Yönlü çizgi örnekleri çıkarılır  
  - Açı tabanlı ortalama piksel vektörleri hesaplanır  
  - Yamalar ve genişletilmiş bölgeler kodlanır  
- Test görüntüsü üzerinden model benzerliği ile segmentasyon yapılır ve morfolojik olarak iyileştirilir.  

### ✅ `Piramit.ipynb`  
- Gaussian Pyramid yöntemiyle 3 farklı çözünürlükte analiz yapılır.  
- Her seviyede:
  - Kenar çıkarımı
  - Çizgi ve yama örnekleme
  - Genişletilmiş bölge kodlama uygulanır.

---

## 🛠️ Kurulum ve Çalıştırma

1. Gerekli kütüphaneleri yükleyin:
```bash
pip install torch torchvision opencv-python scikit-image matplotlib numpy
