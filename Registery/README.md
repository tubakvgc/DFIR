# Registery Analizi
Windows Registry, işletim sistemi ve yüklenmiş yazılımlara dair ayarları içeren kritik bir bileşendir. Kullanıcı hesap bilgileri, donanım cihazlarına ait veriler, yüklenmiş programlar ve sistem yapılandırma bilgileri gibi çok sayıda bilgi bu veritabanında saklanır. Bu yapı, beş ana anahtar grubuna (hive) ayrılır: HKEY_LOCAL_MACHINE (HKLM), HKEY_CURRENT_USER (HKCU), HKEY_CLASSES_ROOT (HKCR), HKEY_USERS (HKU) ve HKEY_CURRENT_CONFIG (HKCC).

Bu hivelar, sistemdeki aygıtlar, kurulu yazılımlar, kullanıcı ayarları ve daha pek çok konuda detaylı bilgileri içermektedir. Bu nedenle, Registry'ye erişim, olaylara dair detaylı bilgiler sağlamak ve şüpheli aktiviteleri tespit etmek için çok faydalı olabilir.

### Windows işletim sisteminde bulunan önemli Registry hive'ları şunlardır:

**SAM (Security Account Manager):**Kullanıcı hesapları ve şifre hash'lerini depolar. Güvenlik açısından oldukça kritik bir veritabanıdır ve genellikle şifre analizi veya kimlik doğrulama bilgilerini incelemek amacıyla kullanılır. Bu veritabanı, kullanıcı hesap bilgilerini, şifre hash'lerini ve grup üyeliklerini içerir.
SAM dosyası, C:\WINDOWS\system32\config veya C:\WINDOWS\system32\config\RegBack dizinlerinde yer alır ve bu dosyayı elde etmek için reg save hklm\sam C:\sam komutu kullanılabilir.
https://github.com/tubakvgc/DFIR/blob/main/Registery/SAM_Analizi.md 

**SYSTEM:** Sistem yapılandırma bilgilerini içerir ve özellikle işletim sistemi ile donanım yapılandırmaları hakkında bilgi sağlar. Bu hive, sistemin yeniden başlatılması sırasında hangi sürücülerin ve servislerin yükleneceği gibi bilgileri tutar; ayrıca donanım yapılandırma bilgileri ve sistem saat ve tarih bilgilerini de içerir.
SYSTEM dosyası da benzer şekilde C:\WINDOWS\system32\config veya C:\WINDOWS\system32\config\RegBack dizininde bulunur ve reg save hklm\system C:\system komutuyla kaydedilebilir.
https://github.com/tubakvgc/DFIR/blob/main/Registery/SYSTEM_Analizi.md

**SOFTWARE:** Sistemde yüklü olan yazılımlar ve bu yazılımlara ait yapılandırma bilgilerini saklar. Bu veritabanı, özellikle sistemde kurulu olan yazılımların bilgilerini, bu programların ayarlarını ve kayıtlı lisans ile ürün anahtarlarını içerir.
SOFTWARE dosyasına da aynı yollarla erişilebilir (C:\WINDOWS\system32\config veya C:\WINDOWS\system32\config\RegBack). Elde edilmesi için reg save hklm\software C:\software komutu kullanılır.
https://github.com/tubakvgc/DFIR/blob/main/Registery/SOFTWARE_Analizi.md

**NTUSER.DAT:** Kullanıcıya özel ayarların saklandığı dosyadır. Her kullanıcının profili için ayrı bir NTUSER.DAT dosyası vardır ve kullanıcının masaüstü ayarları, tarayıcı geçmişi, internet ayarları, çeşitli uygulama ayarları ve kullanıcıya özel kayıt defteri anahtarlarını içerir.
NTUSER.DAT dosyası ise kullanıcı profiline özel olup C:\Users\KullanıcıAdı dizininde yer alır.
https://github.com/tubakvgc/DFIR/blob/main/Registery/NTUSER.dat_Analizi.md






