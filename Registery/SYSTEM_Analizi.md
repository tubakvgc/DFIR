# SYSTEM Dosya Analizi

SYSTEM dosyası, Windows işletim sistemlerinde bilgisayarın sistem yapılandırmasına ilişkin bilgileri barındırır. Bu dosya, bilgisayar adı, zaman dilimi (timezone), son bağlantı kurulan ağlar ve bağlanan USB aygıtları gibi önemli sistem bilgilerini içerir. 

##### SYSTEM dosyasının analizi, genellikle adli bilişim veya güvenlik araştırmalarında kullanılır ve şu bilgileri içerir:

- Bilgisayar Adı: Sistem üzerinde tanımlı olan bilgisayarın adını içerir.
- Timezone Bilgisi: Bilgisayarın saat dilimi ayarlarına ilişkin bilgiyi barındırır.
- Bağlantı Kurulan Son Ağ ve IP Bilgisi: Sistemin en son bağlandığı ağlar ve kullanılan IP adreslerini içerir.
- Bilgisayara Takılan USB Bilgileri: Bilgisayara daha önce takılmış USB aygıtlarının bilgilerini barındırır.

### Dosya Yolu:

- C:\WINDOWS\system32\config
- C:\WINDOWS\system32\config\RegBack
  
Dosyayı Yedekleme Komutu: Registry dosyaları doğrudan çekilemez; bunun yerine aşağıdaki komut ile dosyanın bir kopyası alınabilir:
- reg save hklm\system C:\system

## RegistryExplorer ile Analiz

RegistryExplorer aracı, Registry dosyalarını ya da imaj içindeki Registry kayıtlarını import edip inceleyebilmeyi sağlar. RegistryExplorer, seçilen Registry türüne göre bizim için önemli olabilecek kısımları "Available Bookmarks" bölümünde göstermektedir.

Şimdi dosyayı bir yere kopyalayıalım
- reg save hklm\SYSTEM "C:\Users\Tuba Kavgacı\Desktop\hey\SYSTEM"

![image](https://github.com/user-attachments/assets/2923fcca-dad6-4b03-aefc-b8cf320125d3)

Kopyalanan dosyayı RegistryExplorer aracına import edelim.

"Available Bookmarks" kısmında bilgisayar ismi, timezone bilgisi, bilgisayara takılan usb belleklerin kayıtları, paylaşıma açılmış dosya bilgileri, bağlantı kurulan ağ ve bunların ip adresi vs bilgileri öğrenilebilir.

![image](https://github.com/user-attachments/assets/2c7e5b69-0861-4321-a832-c58bb5b231fd)

Burada görüldüğü gibi iki farklı ağa giriş yapılmıştır. Interfaces bölümünü genişleterek daha önce bağlanmış olduğum diğer ağların kayıtlarını görüntüleyebilirim. Aşağıdaki resimde görüldüğü gibi, 192.168.117.2 IP adresine ait bir ağ bağlantısı kaydı bulunmaktadır.

![image](https://github.com/user-attachments/assets/34b91d2d-4e08-47d9-8d45-84b86bc8b22d)

Mount Devices bölümünde, bilgisayarda daha önce bağlanan (mount edilen) bölümlere ait bilgiler de bulunmaktadır.

![image](https://github.com/user-attachments/assets/2ff061a4-7d35-4030-8a34-cbb85fb93a44)


Hatta, bilgisayarımızın en son ne zaman kapatıldığını (shutdown) gösteren bilgiler de aşağıdaki bölümde yer almaktadır.

![image](https://github.com/user-attachments/assets/d90da945-e6a7-4019-8647-a84fc4a0df46)

Bu değer bir hex değeri olup saat dilimini temsil etmektedir. Bu hex değeri çevirmek için Dcode aracını kullanacağız. İlgili hex verisi alınarak aşağıdaki adımlar izlenir:

1. Hex değerindeki "-" işaretleri kaldırılır ve düzenli bir şekilde hazırlanır.
2. Hazırlanan hex değeri Dcode aracına aktarılır.
3. Dcode üzerinde Tool sekmesinde filtreleme yapılarak sonuçlar yıllara göre gruplandırılır.
Bu işlemler sonucunda elde edilen sonuçlar aşağıdaki gibidir.

![image](https://github.com/user-attachments/assets/fa48cefb-69c7-4cb8-9b9f-069d98da3786)

