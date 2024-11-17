# Amcache Analizi

Amcache.hve dosyası, Windows işletim sisteminde son kullanılan veya yüklü programların kaydını tutar ve adli bilişim analizlerinde oldukça değerli bilgiler sağlar. Bu dosya, özellikle kullanıcı tarafından başlatılan uygulamaları ve bu uygulamaların sistemde ne zaman çalıştırıldığını belirlemek için kullanılır.

## Amcache Dosyalarının Konumları
Amcache dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- Yok
  
#### Windows 7:
- C:\Windows\AppCompat\Programs\RecentFileCache.bcf

#### Windows 10 ve Sonrası:
- C:\Windows\AppCompat\Programs\Amcache.hve

## Analiz
Yukarı da belirtilmiş olan adrese gidilip dosya açılmıştır.
![image](https://github.com/user-attachments/assets/d0e39a06-2def-474a-9073-534be38820ce)

Açılan dosyada dosyaların Türleri değiştirme tarihleri ve boyutları gözükmektedir. Ve dosyalar çok küçük boyutlardadaır. Bu dosyaları parser ederk gerçek veriye ulaşmaya çalışabilriiz.
Bunun için öncelikle dosyaların kopyalayıp başka bir klasörde muhafaza edelim.
Ardından LinkParser aracını kullanarak dosyayı içeri aktaralım.
![image](https://github.com/user-attachments/assets/951948fd-0602-4449-9628-970c5d50e0fc)

LinkParser aracının anlamsız bir şekilde çalışmamasından ötürü başka bir uygulamaya geçiş yaptım. Sanırsam gudubetliğim iş başında :)
Bu süreçte Windows File Analysis aracının kullanarak ilgili dosyayaı seçtim ve aşağıdaki görüntüde bilgileri elde etmiş oldum.
![image](https://github.com/user-attachments/assets/25951380-2c5e-4990-9689-55c4542209f9)

Bu araç sayesinde dosyanın ismi, bulunduğu yol, hangi bilgisayarda olduğu, MAC adresi veya hash değeri gibi pek çok bilgi öğrenilebilir. 
Bu çıkarımlar, adli analizlerde ve değerlendirmelerde oldukça faydalı olabilir.
