# Chest X-ray Görüntü Ön İşleme Proje Özeti ve Aşamaları

Bu projede, [ChestX-ray8 dataset](https://arxiv.org/abs/1705.02315) veri seti kullanılarak göğüs röntgeni görüntüleri üzerinde veri keşfi ve görüntü işleme teknikleri uygulanacaktır.

<img src="https://raw.githubusercontent.com/hardik0/AI-for-Medicine-Specialization/master/AI-for-Medical-Diagnosis/Week-1/xray-image.png" alt="U-net Image" width="300" align="middle"/>

## Proje Aşamaları

### 1. Veri Yükleme
#### 1.1 Kütüphanelerin İçe Aktarılması
* Pandas, Numpy, Matplotlib ve Seaborn gibi kütüphaneler içe aktarılacak.
* `os` modülü kullanılarak dosya yolları belirtilecek.

#### 1.2 Veri Setinin Yüklenmesi
* `train_df` olarak adlandırılan veri çerçevesine veri seti yüklenecek.
* İlk birkaç satır incelenecek ve toplam satır/sütun sayısı ekrana yazdırılacak.

#### 1.3 Veri Özelliklerinin İncelenmesi
* Sütunlardaki veri türleri ve eksik değerler analiz edilecek.
* `PatientId` sütunundaki benzersiz hasta sayısı hesaplanacak.
* Hastaların birden fazla görüntüsünün olup olmadığı kontrol edilecek.

### 2. Görüntü Yükleme ve Görselleştirme
#### 2.1 Rastgele Görüntüler Seçme
* `train_df`'in "Image" sütunundan rastgele 9 görüntü seçilecek.
* Görseller yan yana görselleştirilecek.

#### 2.2 Rastgele Görüntülerin İstatistiksel Özelliklerini Hesaplama
* Her bi görüntü için Maksimum, minimum, ortalama ve standart sapma değerleri hesaplanacak.

#### 2.3 Histogram Çizimi
* Görseller için piksel yoğunluk histogramları oluşturulacak.

### 3. Görüntü İşleme ve İyileştirme
#### 3.1 Kontrast Germe
* Minimum ve maksimum piksel değerlerine göre kontrast germe yapılacak.

#### 3.2 Histogram Eşitleme
* Kontrast germe sonrası histogram eşitleme uygulanacak.

#### 3.3 Gamma Düzeltme
* Görüntünün parlaklığı gamma düzeltme ile ayarlanacak.

### 4. Gürültü Azaltma
#### 4.1 Median ve Gaussian Blur Uygulama
* Gamma düzeltme sonrası median ve gaussian blur uygulanacak ve sonuçları karşılaştırılacak.

### 5. Döndürme ve Ayna Çevirme
#### 5.1 Rastgele Açılarla Döndürme
* Görüntü 0-10 derece arasında rastgele bir açıda döndürülecek.

#### 5.2 Ayna Çevirme
* Görüntü yatay olarak çevrilecek ve sonuç görselleştirilecek.

### 6. Frekans Alanında Filtreleme
#### 6.1 Fourier Dönüşümü ve Filtreleme
* Görüntü frekans alanına dönüştürülecek, düşük frekansları geçiren maske uygulanacak. Ardından ters Fourier dönüşümü ile frekans alanında filtreleme yapılacak.

### 7. Keskinleştirme ve Enterpolasyon
### 7.1 Keskinleştirme
* `Unsharp masking` tekniği ile görüntü keskinleştirilecek.

### 7.2 Bicubic Enterpolasyon
* Görüntü iki kat büyütülerek enterpolasyon yapılacak.
