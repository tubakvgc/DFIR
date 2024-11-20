# MRU (Most Recently Used) Analizi

Windows MRU (Most Recently Used), kullanıcıların son açtığı veya kullandığı dosya ve uygulamaları kayıt altına alan bir sistemdir. Bu sistem, adli bilişim analizlerinde kullanıcı etkinliklerini anlamak ve olay zaman çizelgesi oluşturmak için çok önemli bir bilgi kaynağıdır.

## MRU Dosyalarının Konumları

MRU verileri, Windows Registry ve sistem dosyalarında farklı konumlarda saklanır. En yaygın konumlardan biri şu şekildedir:
- Bilgisayar\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32
Bu konumda, kullanıcının son kullandığı dosya ve klasör bilgileri tutulur.


### MRU Anahtarlarının Anlamları

![image](https://github.com/user-attachments/assets/469ac7f0-31a8-46d2-8627-b59225543bad)

#### CIDSizeMRU
- Kullanıcı tarafından en son erişilen dosya açma veya kaydetme pencerelerinin boyut ve konum bilgilerini tutar. Bu sayede kullanıcı, dosya açma veya kaydetme penceresini yeniden açtığında pencerenin önceki konumunu ve boyutunu hatırlar.

#### LastVisitedPidMRU
- Kullanıcının en son ziyaret ettiği dizinlerin kaydını tutar. Bu, kullanıcının hangi klasörlere göz attığı ve nerelerde çalıştığı bilgilerini verir.

#### LastVisitedPidMRULegacy
- LastVisitedPidMRU anahtarının eski bir sürümüdür. Genellikle eski sistemlerle veya uyumluluk için saklanır. Modern sistemlerde çoğunlukla aynı bilgileri içerir fakat yeni sürümlerinde kullanılmayabilir.

#### OpenSavePidlMRU
- Farklı dosya türleriyle yapılan son açma veya kaydetme işlemlerine dair bilgileri tutar. Bu anahtar altındaki alt klasörler, dosya türlerine göre ayrılmıştır (örneğin docx, pdf, jpg, txt gibi). Her dosya türü için en son açılan veya kaydedilen dosyaların listesi tutulur.
* (yıldız) klasörü, farklı dosya uzantılarına sahip en son açılan verilerin kaydını içerir.

**Not:** Bir dosyanın OpenSavePidlMRU kaydı oluşturabilmesi için, o dosyanın Windows iletişim kutusu aracılığıyla açılmış olması gereklidir.

![image](https://github.com/user-attachments/assets/3de85421-257b-4d8c-b848-43bbaef45aab)

#### RunMRU

- Bilgisayar\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
RunMRU, Windows + R tuş kombinasyonu ile açılan "Çalıştır" kutusuna girilen komutların kaydını tutar. Bu, kullanıcının çalıştırdığı komutlara veya uygulamalara dair önemli bilgiler sağlar.


#### MRU Analiz Araçları

LastActivityView gibi araçlar, kullanıcının son aktivitelerini otomatik olarak toplayarak analiz için kullanılabilecek veriler sunar. Bu sayede, kullanıcının bilgisayarda yaptığı işlemler adım adım izlenebilir.
![image](https://github.com/user-attachments/assets/3be41253-1d7b-46ba-a795-b54f7040f275)

#### MRU Verilerinden Elde Edilebilecek Bilgiler

- Kullanıcının en son hangi dosyaları açtığı veya kaydettiği.
- Klasör gezgini ile hangi klasörlere erişildiği.
- Bilgisayara kurulan yazılımlar.
- Bilgisayarın başlatılma ve kapatılma zamanları.
- Bilgisayar uyku moduna alındıysa bu bilginin kaydı.
- Bir ağ bağlantısı yapıldıysa bunun kaydı.

MRU verileri, kullanıcı etkinliklerini anlamak ve sistemin kullanım örüntülerini analiz etmek için kritik bir rol oynar. Bu bilgiler, adli bilişim incelemelerinde kullanılarak olayın tam olarak nasıl gerçekleştiğini anlamaya yardımcı olur.
