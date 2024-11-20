# USB History Analizi

USB History, bir bilgisayarda daha önce bağlanmış olan USB cihazlarının (örneğin, USB bellekler, harici diskler, klavyeler, fareler gibi) kayıtlarını ifade eder. Windows işletim sistemi, USB cihazları bağlandığında, bu cihazlarla ilgili bilgileri sistemde saklar. Bu bilgiler, cihazın tanımlayıcı verilerinden bağlantı zamanına kadar birçok ayrıntıyı içerir. USB geçmişi analizi, adli bilişimde kullanıcı aktivitelerini anlamak ve sistem üzerinde kullanılan cihazları tespit etmek için kritik bir öneme sahiptir.


**USB Aygıt Bilgileri ve Zaman Bilgileri:**
- **Registry Konumları:**
  - HKLM\SYSTEM\CurrentControlSet\Enum\USB
  - HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR
- **İçerik:**
  - USB aygıtlarının adı ve seri numarası.
  - İlk takılma, son takılma ve son çıkarılma tarihleri.

---

**Mounted Devices (Bağlanan Cihazlar):**
- **Registry Konumu:**
  - HKLM\SYSTEM\MountedDevices
- **İçerik:**
  - Mount edilmiş sürücülerin bilgileri.

---

**USB Cihaz İsimleri:**
- **Registry Konumu:**
  - HKLM\SOFTWARE\Microsoft\Windows Portable Devices\Devices
- **İçerik:**
  - USB cihazlarının isimleri.

---

**Sürücü ve Aygıt Kurulum Logları:**
- **Log Dosyası Konumları:**
  - **Windows XP:**
    - C:\Windows\setupapi.log
  - **Windows 7/8/10:**
    - C:\Windows\INF\setupapi.dev.log
- **İçerik:**
  - Sürücü ve aygıt kurulumlarına dair log kayıtları.
    
## Analiz
USB geçmişine dair kayıtlar, **Registry Explorer** gibi araçlar kullanılarak analiz edilebilir. Live bir sistemde kayıt defterine erişim sağlanarak şu adımlar takip edilebilir:

1. **SYSTEM Hive’i İnceleme:**
   - SYSTEM kayıt defteri seçilir ve USB ile ilgili olan dizinlere gidilir.
   - `USB` ve `USBSTOR` dizinleri görüntülenir.
![image](https://github.com/user-attachments/assets/40e14cd8-50c3-4c0b-954d-e0d6f9eaf9fd)

2. **USBSTOR Dizinindeki Kayıtlar:**
   - `USBSTOR` dizini altında, daha önce bağlanmış cihazlar listelenir.
   - Bir alt dizine geçildiğinde, cihazın seri numarası görüntülenir.
   - Daha da derine inildiğinde, **Properties (Özellikler)** incelenir:
     - **0064:** Cihazın ilk kez bilgisayara hangi gün takıldığını gösterir.
     - **0066:** Cihazın en son bilgisayara takıldığı tarihi gösterir.
     - **0067:** Cihazın bilgisayardan çıkarılma tarihini gösterir.
   - **Son Çıkarma Tarihi** ve **Son Bağlantı Tarihi** arasındaki fark, cihazın ne kadar süre kullanıldığını anlamaya yardımcı olur.

![image](https://github.com/user-attachments/assets/38a4cb21-d0d5-4fdf-a83e-344a8149b64d)

3. **USB Dizininde Benzer İncelemeler:**
   - Yukarıdaki işlemler, aynı şekilde `USB` dizini altında da yapılabilir.
   - Bu dizinde de cihazlara dair benzer bilgiler bulunur.
