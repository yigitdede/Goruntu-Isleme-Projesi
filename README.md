# Goruntu-Isleme-Projesi

Bu proje, 10 farklı hayvan türü (Leopar, Dolphin, Aslan, Tilki, Moose, Tavşan, At, Sincap, Yarasa, Goril) sınıflandırmasını amaçlamaktadır. Görüntü işleme ve derin öğrenme teknikleriyle modelin doğruluğu artırılmaya çalışılmıştır. Ayrıca, modelin manipülasyona karşı dayanıklılığı çeşitli testlerle değerlendirilmiştir.
## İçindekiler
- [Proje Aşamaları](#Proje-Aşamaları)
- [Yararlanılan Teknolojiler](#Yararlanılan-Teknolojiler)
- [Görsel Yükleme ve Etiketleme](#Görsel-Yükleme-ve-Etiketleme)
- [Veri Artırma](#Veri-Artırma)
- [CNN Modeli](#CNN-Modeli)
- [Eğitim Aşaması](#Eğitim-Aşaması)
- [Manipülasyon](#Manipülasyon)
- [Sonuçlar ve Değerlendirme](#Sonuçlar-ve-Değerlendirme)
- [Çözüm Önerileri](#Çözüm-Önerileri)
- [Colab Proje Linki](#Colab-Proje-Linki)

## Proje Aşamaları

1. Model Kurulumu ve Eğitimi
Derin Konvolüsyonel Sinir Ağı (CNN) modeli kurularak eğitilmiştir.
2. Işık Manipülasyonu ile Test
Modelin doğruluğu, test resimlerinin farklı ışık koşulları altında manipüle edilerek test edilmiştir.
3. Renk Sabitliği Algoritması
Işık manipülasyonu sonucu oluşan doğruluk düşüşü minimize edilmek amacıyla renk sabitliği algoritması uygulanmıştır.
4. Test Sonuçları ve Raporlama
Manipülasyon ve renk sabitliği uygulamaları sonrası modelin performansı karşılaştırılmış ve raporlanmıştır.
Veri Seti
Proje, hayvan görselleri içeren geniş bir veri setini kullanmaktadır. Bu veri seti, her bir görseli doğru bir şekilde etiketleyerek modelin eğitiminde kullanılmakta ve doğruluğunu artırmaya yardımcı olmaktadır.

## Kullanılan Teknolojiler

-Python

-TensorFlow/Keras

-OpenCV

-NumPy


## Görsel Yükleme ve Etiketleme
cv2.imread() ile görseller yüklenir ve modelin eğitimine uygun şekilde etiketlenir.
Görseller, 0-1 aralığında normalize edilir.

## Veri Artırma

Eğitim verileri üzerinde veri artırma işlemleri (train_datagen) ile resimler döndürülür, kaydırılır, kırpılır ve yakınlaştırılır.
Test verileri sadece normalizasyon ile işlenir (test_datagen).

## CNN Modeli

Modelde 4 adet konvolüsyonel katman (Conv2D) ve her katmandan sonra max pooling uygulanmıştır.
Batch normalization, modelin daha hızlı öğrenmesini sağlar.
Modelde, dropout katmanları aşırı öğrenmeyi engellemek için kullanılmıştır.

## Eğitim Aşaması

TestAccuracyCallback sınıfı ile modelin her epoch sonunda test doğruluğu izlenir.
ModelCheckpoint ile en iyi model kaydedilir.
EarlyStopping ile aşırı öğrenme engellenir.

## Manipülasyon

Test setindeki görsellerin parlaklık ve kontrast manipülasyonu yapılır.
Manipüle edilen görseller kaydedilir ve modelin doğruluğu test edilir.

## Sonuçlar ve Değerlendirme

Performans Değerlendirmesi
Orijinal Test Seti: Modelin doğruluğu %55.23.
Manipüle Edilmiş Test Seti: Görsellerde kontrast artırma ve döndürme işlemleri sonrası doğruluk %11.85'e düşmüştür.
Renk Sabitliği Uygulanan Test Seti: Renk sabitliği uygulanmış görsellerde doğruluk %11.92'ye çıkmıştır.

## Sonuçlar:

Model, görsel manipülasyonlara karşı duyarlı ve renk düzeltme gibi yöntemler sınırlı bir iyileşme sağlamıştır. Bu, modelin manipülasyona karşı dayanıklı olmadığını ve iyileştirmeler yaparak daha güçlü hale getirilmesi gerektiğini göstermektedir.

## Çözüm Önerileri:
Daha fazla veri ve veri artırma teknikleri kullanılmalıdır.
Model mimarisi iyileştirilmelidir.
Modelin manipülasyona dayanıklılığını artırmaya yönelik ek yöntemler kullanılmalıdır.

## Colab Proje Linki

Projenin tamamına ve kod örneklerine [buradan ulaşabilirsiniz](https://colab.research.google.com/drive/1llZCIpSDs6PyaNfH6ufwspA7B0AjZI8N#scrollTo=iMmy_VAgS3N9).
