# Powershell Analizi

Amcache.hve dosyası, Windows işletim sisteminde son kullanılan veya yüklü programların kaydını tutar ve adli bilişim analizlerinde oldukça değerli bilgiler sağlar. Bu dosya, özellikle kullanıcı tarafından başlatılan uygulamaları ve bu uygulamaların sistemde ne zaman çalıştırıldığını belirlemek için kullanılır.

## Powershell Dosyalarının Konumları
PowerShell geçmiş kayıt dosyası aşağıdaki konumlarda bulunur:

#### Windows XP:
- Yok
  
#### Windows 7:
- Varsayılan olarak yok, ancak bir modül yüklenmesi durumunda aktifleşir.


#### Windows 10 ve Sonrası:
- C:\Users\[UserName]\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt

## Analiz
Yukarı da belirtilmiş olan adrese gidilip dosya açılmıştır.
![image](https://github.com/user-attachments/assets/d2d46d3e-6c04-45a3-a0bc-25da79031aba)

Dosya, bir metin dosyası formatında olduğundan herhangi bir metin düzenleyici ile kolayca açılabilir. Dosya açıldığında, aşağıdaki gibi PowerShell üzerinden yazılmış tüm komutların bir listesi elde edilmiştir:

![image](https://github.com/user-attachments/assets/67bb2698-3d82-4ab7-8348-2717b83bbc0b)

#### Çıkarımlar
Bu analiz sayesinde:

1. Saldırgan Etkinlikleri:
Saldırganın gerçekleştirdiği tüm etkinlikleri ve yazdığı komutları detaylı bir şekilde inceleyebiliriz.
2. Komut Analizi:
Zararlı eylemler için kullanılan PowerShell komutlarını tespit edebiliriz.
3. Adli Bilişim ve Olay Müdahalesi:
Bir saldırı sırasında veya sonrasında sistem üzerinde yürütülen komutları belirleyerek olay zaman çizelgesi oluşturabiliriz.



