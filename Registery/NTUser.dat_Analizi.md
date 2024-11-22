# NTUSER.DAT Dosya Analizi

NTUSER.DAT dosyası, Windows işletim sistemlerinde her kullanıcı için ayrı olarak bulunan bir yapılandırma dosyasıdır. Bu dosya, kullanıcının profiline özgü ayarları ve geçmişe dair bilgileri barındırır. 

##### NTUSER.DAT dosyasının analizi, genellikle adli bilişim veya güvenlik araştırmalarında kullanılır ve şu bilgileri içerir:

- Çalıştırılan Programların Analizi: Kullanıcının hangi programları çalıştırdığı bilgisi.
- Açılan/Oluşturulan Dosyaların Analizi: Kullanıcı tarafından açılan ya da oluşturulan dosyaların kayıtları.
- Takılan USB Bilgileri: Kullanıcının takmış olduğu USB cihazlarına ait bilgiler.
- WordWheelQuery Bilgileri: Kullanıcının arama geçmişi kayıtları.


### Dosya Yolu:
- C:\Users\KullanıcıAdı

Dosyayı Yedekleme: 
- Registry dosyalarını almak için aşağıdaki komut veya araçlar kullanılabilir
- FTK Imager Lite gibi araçlar kullanılarak NTUSER.DAT dosyasının bir kopyası alınabilir.


## RegistryExplorer ile Analiz

RegistryExplorer aracı, Registry dosyalarını ya da imaj içindeki Registry kayıtlarını import edip inceleyebilmeyi sağlar. RegistryExplorer, seçilen Registry türüne göre bizim için önemli olabilecek kısımları "Available Bookmarks" bölümünde göstermektedir.

Şimdi dosyayı bir yere kopyalayıalım
- FTKİmager ile export edelim.
  
![image](https://github.com/user-attachments/assets/875277c2-614d-4f8b-9bed-46794751ffb1)

Kopyalanan dosyayı RegistryExplorer aracına import edelim.

"Available Bookmarks" kısmında Run, Recent.docs, systernals/autorun, RunMRU bölümleri zaten artifact kısmında daha detaylı anlatılmaktadır. Bunların haricinde UserAssiste bölümünde bilgisyardaki GUI yani arayüz olan ve çalıştırılan uygulamlara ait detaylar görülmektedir. CE ile başlayıp EA ile biten değerde uygulamalra ait veriler vardır. Uygulamalrın kaç kez çalıştırıldığı, Kaç gün kaç dk çalıştırıldığı ve en son ne zman çalışmış buna bağlı veirler gözükmektedir.

![image](https://github.com/user-attachments/assets/4e957a6b-2baf-4ffb-8d28-a7a5bdfc1046)

bunlar haricinde printer dosyalarının da bilgileri buradan bakılabilir. 
