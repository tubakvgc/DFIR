# SAM Dosya Analizi

SAM dosyası, Windows işletim sistemlerinde kullanıcı hesaplarına ilişkin bilgileri barındıran ve güvenli bir şekilde şifrelenmiş bir veri tabanıdır. SAM, "Security Account Manager" (Güvenlik Hesap Yöneticisi) anlamına gelir ve NTLM hash değerlerini tutarak kullanıcı kimlik doğrulamasında önemli bir rol oynar. Windows sistemlerinde genellikle C:\Windows\System32\Config\SAM dizininde bulunur. Ancak, bu dosyaya erişim sınırlıdır ve yalnızca özel yöntemlerle okunabilir.

##### SAM dosyasının analizi, genellikle adli bilişim veya güvenlik araştırmalarında kullanılır ve şu bilgileri içerir:

- Son Giriş Tarihi: Kullanıcının sisteme son başarılı giriş yaptığı tarihi belirtir. Bu bilgi, kullanıcı etkinliklerini takip etmek için kullanılır.
- Son Hatalı Giriş Tarihi: Sisteme yapılan son başarısız giriş denemesini gösterir. Bu, potansiyel saldırı girişimlerini veya unutulmuş parolaları belirlemek için değerlidir.
- Son Parola Değiştirme Tarihi: Kullanıcının parolasını en son değiştirdiği tarihi belirtir. Güvenlik politikalarına uyumluluğu denetlemek için önemlidir.
- Kullanıcı ve Grup Bilgileri: Sistemde kayıtlı kullanıcıların kimlik bilgilerini ve bunların hangi gruplara dahil olduğunu içerir. Kullanıcı yetkilendirmesi ve erişim denetimi açısından önemli bilgiler sağlar.


##### SAM (Security Account Manager):

Dosya Yolu:
- C:\WINDOWS\system32\config
- C:\WINDOWS\system32\config\RegBack

Dosyayı Yedekleme Komutu: REgistery dosyaları direkt olarak çekilemez bunları kaydetmek için aşağıdaki komut kullanılır.
- reg save hklm\sam C:\sam

## RegistryExplorer ile Analiz

RegistryExplorer aracı, Registry dosyalarını ya da imaj içindeki Registry kayıtlarını import edip inceleyebilmeyi sağlar. RegistryExplorer, seçilen Registry türüne göre bizim için önemli olabilecek kısımları "Available Bookmarks" bölümünde göstermektedir.

Şimdi dosyayı bir yere kopyalayıalım
- reg save hklm\SAM "C:\Users\Tuba Kavgacı\Desktop\hey\SAM"

![image](https://github.com/user-attachments/assets/da543c95-359b-4d0b-9b80-79b502a2d8db)

Kopyalanan dosyayı RegistryExplorer aracına import edelim.

"Available Bookmarks" kısmında Users bölümü var burada userlara baktığımız da bazı userların admin grubunda olduğu görülmüştür.
Tuba Kavgacı kullanıcısı toplamda  373 kez login işlemi yapmıştır.
Parola değişiklikleri tarihleri ilk giriş tarihleri vs bilgileri bulunmaktadır.

![image](https://github.com/user-attachments/assets/bdd8b372-8b74-4d48-bdd1-b13c29a9d2a2)

RegistryExplorer ile SAM dosyasının analizi sayesinde sistem kullanıcılarına dair detaylı bilgi elde edilebilir. Bu bilgiler, adli bilişim ve sistem güvenliği çalışmaları için kritik öneme sahiptir.








































