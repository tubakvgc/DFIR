# Amcache Analizi

Amcache.hve dosyası, Windows işletim sisteminde son kullanılan veya yüklü programların kaydını tutar ve adli bilişim analizlerinde oldukça değerli bilgiler sağlar. Bu dosya, özellikle kullanıcı tarafından başlatılan uygulamaları ve bu uygulamaların sistemde ne zaman çalıştırıldığını belirlemek için kullanılır.

## Amcache Dosyalarının Konumları
Amcache dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- Yok
  
#### Windows 7:
- C:\Windows\AppCompat\Programs\RecentFileCache.bcf

#### Windows 10 ve Sonrası:
- C:\Windows\AppCompat\Programs\Amcache.hve

## Analiz
Yukarı da belirtilmiş olan adrese gidilip dosya açılmıştır.
![image](https://github.com/user-attachments/assets/9004908a-943b-4320-948a-34f45bd66ed1)

Açılan dosyada dosyaların türleri değiştirme tarihleri ve boyutları gözükmektedir. Bu dosyaları parser ederek gerçek veriye ulaşmaya çalışabilriz.
Bunun için öncelikle dosyaların kopyalayıp başka bir klasörde muhafaza edelim.
Ardından AmcacheParser aracını kullanacağız. Aracın konumunun olduğu dosyaya gidip cmd çalıştıralım.
AmcacheParser aracının kulanarak aşağıdaki komutu cmd yazdım ve parser işlemi başladı.
- AmcacheParser.exe -f "C:\Users\Tuba Kavgacı\Desktop\amcache\Amcache.hve" --csv "C:\Users\Tuba Kavgacı\Desktop\amcache"
![image](https://github.com/user-attachments/assets/c3722f6b-117e-406a-9aec-13c7ffdc9100)
![image](https://github.com/user-attachments/assets/6e3f955b-1ccd-49e6-91c5-98c96b260693)

Belirtilen çıktı dizinine gidip csv dosyaları eklenmiş mi kontrol sağlanıyor.
![image](https://github.com/user-attachments/assets/911c856a-1840-4ea6-847f-25effdfd0864)

Burada birden fazla çıktılar olduklarını görmekteyiz bunların içlerine bakmadan önce ne olduklarını aşağıda belirttim.
#### 1. Amcache_DeviceContainers.csv
  İçerik: Sistemde bulunan cihazların bilgilerini içerir.
Örnek Veriler:
- Takılı cihazlar (örneğin USB bellekler, harici diskler).
- Bu cihazların benzersiz kimlikleri ve sürücü bağlantı bilgileri.
#### 2. Amcache_DevicePnps.csv
 İçerik: Sistem tarafından tanınan cihazların "Plug and Play" (PnP) bilgilerini içerir.
Örnek Veriler:
- Donanım kimlikleri.
- PnP sürücü bilgileri (örn. donanım tanımları, sürücü yolları).
#### 3. Amcache_DriveBinaries.csv
 İçerik: Sistemde kullanılan sürücülerin ve ikili dosyaların detaylarını içerir.
Örnek Veriler:
- Sürücü yolları.
- İkili dosyaların sürümleri, üretici bilgileri ve SHA-1 hash değerleri.
#### 4. Amcache_DriverPackages.csv
 İçerik: Sistemde yüklü sürücü paketlerini içerir.
Örnek Veriler:
- Sürücü paketlerinin yüklenme tarihleri.
- Sürücülerin üreticileri ve sürüm bilgileri.
#### 5. Amcache_ShortCuts.csv
 İçerik: Windows'ta oluşturulan kısayol (shortcut) bilgilerini içerir.
- Örnek Veriler:
- Kısayolun hedef dosyası.
- Kısayolun oluşturulma ve son kullanım tarihleri.
#### 6. Amcache_UnassociatedFileEntries.csv
 İçerik: Sistemde yüklü, ancak bir programla ilişkilendirilmemiş dosya bilgilerini içerir.
Örnek Veriler:
- Orphaned (yetim) dosyalar.
- Bu dosyaların oluşturulma tarihleri, yolları ve hash değerleri.

Bu araç sayesinde dosyanın ismi, bulunduğu yol, hangi bilgisayarda olduğu, MAC adresi veya hash değeri gibi pek çok bilgi öğrenilebilir. 
Bu çıkarımlar, adli analizlerde ve değerlendirmelerde oldukça faydalı olabilir.

20241118143401_Amcache_UnassociatedFileEntries dosyasının içine girererk analiz ettiğimizde aşağıdaki bilgilere erişebilmekteyiz. 
![image](https://github.com/user-attachments/assets/af727b7b-1b86-4b98-b070-93ec041dcade)

- Dosyaların tam yolu ve hangi klasörlerde bulunduğu.
- Son değiştirilme tarihleri ve oluşturulma tarihleri.
- Hash değerleri (SHA1), dosya bütünlüğünü kontrol etmek için kullanılabilir.
- Dosyanın boyutu, ürün adı ve sürüm bilgileri.
- Dosyanın türü (örneğin: 32-bit mi 64-bit mi).
- Gömülü bir yazılım mı yoksa üçüncü parti bir yazılım mı olduğu bilgileri.

20241118143401_Amcache_DevicePnps dosyasının içine girererk analiz ettiğimizde aşağıdaki bilgilere erişebilmekteyiz. 
![image](https://github.com/user-attachments/assets/ebf22d91-f446-4289-9639-7173f662bb1f)

- Sürücünün oluşturulma tarihi DriverDate sütununda belirtilir.
- Donanım kimliği HWID sütununda yer alır.
- Sürücünün hangi hizmet ile yönetildiği Service sütununda gösterilir.
- Sürücü adı ve açıklaması DriverName ve DriverDesc sütunlarında bulunur.
- Sürücünün üreticisi Manufacturer sütununda belirtilir.
- Sürücünün sürüm numarası DriverVersion sütununda yer alır.
- Aygıtın bağlı olduğu sınıf Class sütununda belirtilir.
- Aygıtın sistemdeki benzersiz adı KeyName sütununda gösterilir.

Ve diğer dosyalar içinde genel bilgiler aşağıdakilerine erişilebilir.
![image](https://github.com/user-attachments/assets/6f6b4c01-6451-4f51-b78c-946529afd167)
![image](https://github.com/user-attachments/assets/3f84ebf8-2f6a-4a5a-88f3-36d4b57fd4ab)
![image](https://github.com/user-attachments/assets/7f7c1bfe-cf2e-4e9e-a2df-0d96a7470ea6)

- Her satır için benzersiz bir anahtar adı içerir.
- Dosyanın tam konumunu veya ilişkilendirildiği yolu belirtir.
- Dosyanın veya girdinin son yazılma zamanı.
- Sürücünün veya bileşenin oluşturulma tarihi.
- Donanım Kimliği, aygıtların benzersiz tanımlayıcısıdır.
- Sürücü dosyasının adı ve işletim sistemiyle ilişkisi.
- İlgili sürücünün veya bileşenin yönetildiği hizmet adı.
- Donanımın veya sürücünün üreticisi.
- Dosyanın veya sürücünün sürüm bilgisi.
- Yazılım veya donanım bileşenine ait ürün ve sürüm bilgileri.
- Sürücünün dijital olarak imzalanıp imzalanmadığını belirtir.
- Sürücünün Windows’un içinde gelen bir bileşen olup olmadığını gösterir.

Analiz sonlanmış olur amcache bilgileri 
