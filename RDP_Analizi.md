# RDP Analizi

RDP (Remote Desktop Protocol), sistemlere uzaktan erişim sağlamak için yaygın olarak kullanılan bir protokoldür. RDP aktivitelerinin izlenmesi ve analizi, güvenlik olaylarını tespit etmek ve yetkisiz erişimleri belirlemek açısından kritik öneme sahiptir. Bu analizde, RDP bağlantılarının izlenmesi ve ilgili sistem artefaktlarının nasıl kullanılacağına odaklanacağız.

## RDP Dosyalarının Konumları
RDP dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- C:\Windows\System32\winevt\Logs
  
#### Windows 7:
- C:\Windows\System32\winevt\Logs

#### Windows 10 ve Sonrası:
- C:\Windows\System32\winevt\Logs
- C:\Users\<KullanıcıAdı>\AppData\Local\Microsoft\Terminal Server Client\Cache

## Analiz

### Tablo 1: Uzak Masaüstü (RDP) Event ID Bilgileri

| **Event ID** | **Açıklama**                 | **İşletim Sistemi**                         |
|--------------|------------------------------|---------------------------------------------|
| 528          | Başarılı giriş işlemi.       | Windows Server 2000/2003                   |
| 529          | Başarısız giriş işlemi.      | Windows Server 2000/2003                   |
| 538          | Başarılı çıkış işlemi.       | Windows Server 2000/2003                   |
| 540          | Ağ üzerinden başarılı giriş. | Windows Server 2000/2003                   |
| 4624         | Başarılı giriş işlemi.       | Windows XP, 7, Vista, 8, 10, Server 2008   |
| 4625         | Başarısız giriş işlemi.      | Windows XP, 7, Vista, 8, 10, Server 2008   |

### Tablo 2: Event ID 4624 – Başarılı Giriş Türleri

| **Giriş Tipi** | **Açıklama**                                                                                                                               |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 2              | **Etkileşimli oturum açma** (Kullanıcı bilgisayarın yerel klavyesini ve ekranını kullanarak oturum açtığında oluşur.)                       |
| 3              | **Ağ oturumu açma** (Kullanıcı uzak dosya paylaşımına veya yazıcılara eriştiğinde oluşur.)                                                 |
| 4              | **Toplu oturum açma** (Zamanlanmış görevler sırasında, Windows Zamanlayıcı ile başlatıldığında oluşur.)                                     |
| 5              | **Hizmet oturumu açma** (Bir hizmeti başlatmak için hizmetler ve hizmet hesapları oturum açtığında oluşur.)                                 |
| 7              | **Oturum açma kilidini açma** (Bir kullanıcı Windows makinesinin kilidini açtığında oluşur.)                                               |
| 8              | **NetworkClearText oturumu açma** (Kullanıcı bir ağ üzerinden oturum açarken parola düz metin olarak gönderildiğinde oluşur.)              |
| 9              | **Kimlik bilgileri oturumu açma** (Kullanıcı RunAs komutunu kullanarak bir uygulama çalıştırdığında oluşur.)                                |
| 10             | **Uzaktan Etkileşimli oturum açma** (Kullanıcı, Terminal Hizmetleri veya Uzak Masaüstü gibi RDP tabanlı uygulamalarla oturum açtığında oluşur.) |
| 11             | **Önbellek Etkileşimli oturum açma** (Kullanıcı, oturum bilgilerini önbellekten alarak oturum açtığında oluşur.)                           |



![image](https://github.com/user-attachments/assets/4fba891d-c069-472e-8a0d-333c3cf7331b)

Bu diizn altında bilgisayarda bulunan tüm log ayıtları görünütleyebiliriz.
RDP bağlantıları için iki özel dosya bakılması gerekir. Bunlar; Security.evtx ve Microsoft-Windows-TerminalServices-LocalSessionManager%4Operational.evtx dosyasıdır.

cmd bu komutu girerek .csv olarak log dosyasını çıkartıyoruz. 
- C:\Users\Tuba Kavgacı\Downloads\Training_Tools\Training Tools\EvtxExplorer>EvtxECmd.exe -f "C:\Users\Tuba Kavgacı\Desktop\hey\Security.evtx" --csv ./ --
csvf security.csv

![image](https://github.com/user-attachments/assets/f8c631bb-4bb9-4bfb-b3db-6110f5f1eb17)

Log dosyasını bu şekilde ayrıştırabiliriz. peki cache dosyasını nasıl ayrıştırıırz. 
Cache dosyaları içinde aşağıdaki komutu cmd yazarak ayrıştırabiliriz. Bu durum için pthon yazılımının olması gerekmektedir.
- python bmc-tools.py -s "C:\Users\Tuba Kavgacı\AppData\Local\Micr
osoft\Terminal Server Client\Cache\Cache0000.bin" -d output

Bu ayrıştırma sonrasında küçük küçük icon resim verileri ortya çıkacaktır.
![image](https://github.com/user-attachments/assets/e567b1c3-5cd6-456a-81b6-070b710e278e)



**NOT:** NLY özelliği, Windows'un RDP oturumlarını daha güvenli bir şekilde açmasını sağlar. Bu özellik sayesinde Windows, çeşitli saldırılara, özellikle DDOS saldırılarına karşı korunabilir. NLY özelliği aktif olduğunda, 10 numaralı ID tipi (Uzaktan Etkileşimli Oturum Açma) sistem tarafından 7 numaralı ID tipi (Oturum Açma Kilidini Açma) olarak kaydedilir. Bu, oturumun daha güvenli bir şekilde başlatıldığını ve kilit açma işlemi gibi işlem gördüğünü ifade eder.




