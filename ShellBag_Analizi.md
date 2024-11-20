# ShellBag Analizi

ShellBag, Windows işletim sisteminde kullanıcıların gezdiği klasörlerin ve bu klasörlerde yaptığı işlemlerin kayıt altına alındığı bir veri yapısıdır. Bu kayıtlar, Windows Registry'de saklanır ve kullanıcıların klasörlerle ilgili tercihlerini (görünüm ayarları, boyut, sıralama gibi) takip etmek için kullanılır. ShellBag analizi, bu verilerin çıkarılması ve incelenmesi yoluyla bir kullanıcının dosya sisteminde gezinti geçmişini anlamak için yapılan bir adli bilişim tekniğidir.

## ShellBag Dosyalarının Konumları
ShellBag verileri genellikle iki önemli dosyada saklanır:

## 1. NTUSER.DAT
Bu dosya, her kullanıcı için bireysel oturum verilerini saklar. Kullanıcı bazlı Registry bilgilerini içerir.

#### Windows XP:
- C:\Documents and Settings\username\NTUSER.DAT
  
#### Windows 7:
- C:\Users\username\NTUSER.DAT

#### Windows 10 ve Sonrası:
- C:\Users\username\NTUSER.DAT


## 2. UsrClass.dat
Bu dosya, kullanıcıların klasörle ilgili tercihlerini ve masaüstü düzenlerini içeren ek bilgileri tutar.

#### Windows XP:
- Yok
  
#### Windows 7:
- C:\Users\username\AppData\Local\Microsoft\Windows\UsrClass.dat

#### Windows 10 ve Sonrası:
- C:\Users\username\AppData\Local\Microsoft\Windows\UsrClass.dat


## Analiz
ShellBags Explorer aracını kullanarak şuan bilgisayardaki otomatik shellbag dosyaalrını görebiliriz.
![image](https://github.com/user-attachments/assets/10c23ea8-9a02-47ad-9790-1ef08eee5a55)


Adli bilişim araçları (FTK Imager veya benzeri) kullanarak ilgili dosyalara erişim sağlanabilir. Örneğin, aşağıdaki gibi C:\Users\Tuba Kavgacı dizinine gidilerek NTUSER.DAT ve UsrClass.DAT ilgili log dosyaları görüntülenebilir:


![image](https://github.com/user-attachments/assets/f9cd4324-2242-4f37-99de-cd1268d26c96)

![image](https://github.com/user-attachments/assets/f05c43f8-9022-47f0-9b67-168402e5f111)

Export İşlemi
- Dosyaları sağ tıklayarak Export edin.
- Çıkarılan dosyaları analiz etmek için komut satırında ilgili aracı çalıştırın.

ShellBag verilerini parser etmek için SBECmd aracı kullanılabilir. Aşağıdaki adımları takip edin:

- Çıkardığınız dosyaları bir klasöre (örneğin, C:\Users\Tuba Kavgacı\Desktop\hey) yerleştirin.
- SBECmd aracını kullanarak dosyaları CSV formatına çevirin. Komut:

![image](https://github.com/user-attachments/assets/cd471bef-f035-40a9-bc4b-290240c22a33)

Komut çalıştırıldıktan sonra veriler CSV formatında belirtilen hedef klasöre kaydedilir.

![image](https://github.com/user-attachments/assets/0f14aa98-8668-47cc-b8bd-9ba84e7c57a5)

.csv dosyasını açarak artık analizimizi gerçekleştirebilriiz.
