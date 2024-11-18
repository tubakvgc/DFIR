# Shimcache Analizi

Shimcache (AppCompatCache), Windows işletim sisteminde uyumluluk verilerini tutar ve özellikle çalıştırılan veya yüklenen uygulamalar hakkında bilgi sağlar. Adli bilişim analizlerinde kullanılarak, sistemde çalıştırılmış olabilecek uygulamaların izlerini bulmaya olanak tanır.

## Shimcache Dosyalarının Konumları
Shimcache dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatibility
  
#### Windows 7:
- SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache

#### Windows 10 ve Sonrası:
- SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache


## Analiz
himcache verileri doğrudan Registry (Kayıt Defteri) dosyalarından elde edilir. Ancak, bu dosyalar sistem tarafından kilitlendiği için doğrudan erişim sağlanamaz. Bu nedenle, aşağıdaki adımlar izlenir:

1. Komut Kullanarak SYSTEM Dosyasını Kopyalama
Aşağıdaki komut kullanılarak SYSTEM dosyasını belirtilen konuma export edebilirsiniz:
reg save hklm\SYSTEM "C:\Users\Tuba Kavgacı\Desktop\SYSTEM"
2. FTK Imager Kullanarak Export Etme
Alternatif olarak, FTK Imager aracı ile C:\Windows\System32\config dizininden SYSTEM dosyasını dışarı aktarabilirsiniz:

C:\Windows\System32\config dizinine gidin.
İlgili dosyaya sağ tıklayıp Export seçeneğini seçin.
  
![image](https://github.com/user-attachments/assets/2328f33b-3b30-42d2-8422-1e625ff54407)


Export ettiğimiz SYSTEM dosyasını FTK imager üzerinden de alabiliriz. Bilgisayardaki Registery dosyları C:\Eindows\System32\config dizini altında bulunmaktadır. Bu bölüme gidip iligli dosyayı sağ click eder dışarı aktarabiliriz.
Export işlemlerinden sonra REgRipper.exe aracı kullanrak önce SYSTEM ardından out dizini belirtilere Aşağıdaki şekilde çalıştırılıp parser işlemi başlatılıyor.

![image](https://github.com/user-attachments/assets/fc42c779-afd4-46a0-94ad-c0101b4b1348)                                                                                          

Çıkarttığımız dizine gidere .txt içindeki dosyayı okuyabiliriz ya da bunu .csv çevirerek okumayı kolaylaştırabiliriz. 

![image](https://github.com/user-attachments/assets/f10c45b4-3e0b-4e46-b2ee-9ee49b86c2d6)

#### Çıkarım
Shimcache parser işlemi sonrası, çalıştırılmış uygulamalar, geçici dosyalar, işletim sistemi bileşenleri, ürün bilgileri, güncellemeler ve kullanıcı faaliyetleri hakkında detaylı bilgiler elde edilmiştir. Bu veriler, adli analizler, sistem aktivitelerinin izlenmesi ve zararlı yazılım analizleri için kullanılabilir.






