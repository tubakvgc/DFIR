# SOFTWARE Dosya Analizi

SOFTWARE dosyası, Windows işletim sisteminde yüklü yazılımlar ve sistem yapılandırmaları ile ilgili bilgileri barındırır. Bu dosya, işletim sistemi adı ve sürümü, yüklü veya kaldırılmış yazılımlar, ağ bağlantıları gibi kritik bilgileri içerir.

##### SOFTWARE dosyasının analizi, genellikle adli bilişim veya güvenlik araştırmalarında kullanılır ve şu bilgileri içerir:

- İşletim Sisteminin Adı ve Sürümü: Sistem üzerinde kurulu işletim sisteminin detaylı bilgilerini içerir.
- İşletim Sisteminin Kurulum Tarihi: Windows'un ilk kez kurulduğu tarihi belirtir.
- Yüklü Yazılımlar: Sistemde kurulu olan yazılımların detaylarını barındırır.
- Kaldırılan Yazılımlar: Daha önce kaldırılmış yazılımlara ilişkin kayıtları içerir.
- Bağlantı Kurulan Ağ Bilgileri: Sistemin bağlandığı ağlar ve IP bilgilerini barındırır.

### Dosya Yolu:
- C:\WINDOWS\system32\config
- C:\WINDOWS\system32\config\RegBack

Dosyayı Yedekleme Komutu: Registery dosyaları direkt olarak çekilemez bunları kaydetmek için aşağıdaki komut kullanılır.
- reg save hklm\software C:\software

## RegistryExplorer ile Analiz

RegistryExplorer aracı, Registry dosyalarını ya da imaj içindeki Registry kayıtlarını import edip inceleyebilmeyi sağlar. RegistryExplorer, seçilen Registry türüne göre bizim için önemli olabilecek kısımları "Available Bookmarks" bölümünde göstermektedir.

Şimdi dosyayı bir yere kopyalayıalım
- reg save hklm\SOFTWARE "C:\Users\Tuba Kavgacı\Desktop\hey\SOFTWARE"

![image](https://github.com/user-attachments/assets/8e4be581-ee3b-4a4b-bf04-5fc459f144df)

Kopyalanan dosyayı RegistryExplorer aracına import edelim.

"Available Bookmarks" kısmına geçelim. Buradaki LogonUI bölümü altında, bilgisayara en son giriş yapmış kullanıcıya ait detaylar görülmektedir. Giriş yapan kullanıcının SID numarası da bu bölümden görüntülenebilir. Ayrıca, NetworksList kısmına girildiğinde bilgisayarın kurmuş olduğu tüm ağ bağlantıları görülebilir.

![image](https://github.com/user-attachments/assets/29dbcf6b-94e9-4878-8b29-8a7ebf13afa6)

Run dizini altında, bilgisayarın açılışında otomatik olarak başlatılan uygulamalara ait detaylar görüntülenmektedir.

![image](https://github.com/user-attachments/assets/635c5c2b-f728-4013-9673-6f45b8821671)

Bilgisayara sonradan kurulan ve kaldırılan yazılımların listeleri, Software/CurrentVersion/Uninstall bölümünde bulunmaktadır.

![image](https://github.com/user-attachments/assets/7cb8fe09-6b28-42e7-b8e1-6313ead066b0)

Daha sonra Hives sekmesine geçerek işletim sistemine ait bilgileri inceleyebiliriz. Root/Microsoft/WindowsNT/CurrentVersion bölümünü açarak aşağıdaki gibi işletim sistemiyle ilgili pek çok bilgiye ulaşabiliriz.

![image](https://github.com/user-attachments/assets/0fe24725-9130-4585-a483-7431d1cff877)

Yukarıdaki işletim sisteminin ilk kurulma tarihi için InstallDate içindeki veriyi alıyoruz ve aşağıdaki gibi bir tarih dönüştürücü kullanarak dönüştürüyoruz. Bu işlem, timestamp zaman dilimini, bizim normal zaman dilimimize çevirmemizi sağlar.
- https://www.epochconverter.com/ 

![image](https://github.com/user-attachments/assets/667b1b10-2106-4066-bde2-25b320473f7e)
