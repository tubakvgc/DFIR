# LNK Dosyası (Kısayol) Analizi

LNK dosyaları, Windows işletim sisteminde kullanılan kısayol dosyalarıdır. Bu dosyalar, kullanıcının belirli bir dosyaya veya uygulamaya hızlıca erişmesini sağlar. LNK dosyaları, adli bilişim açısından oldukça değerlidir çünkü kullanıcının belirli bir dosyayı açıp açmadığını, dosyanın nerede bulunduğunu, dosyanın son açılma zamanını ve diğer meta verileri içerir. LNK dosyaları sayesinde, kullanıcı aktivitelerini ve dosya erişim geçmişini detaylı bir şekilde analiz etmek mümkündür. Bu veriler, özellikle şüpheli dosya erişimlerini tespit etmek ve kullanıcının geçmişte hangi dosyalara eriştiğini belirlemek için kullanılır.

## LNK Dosyalarının Konumları
LNK dosyaları, farklı Windows sürümlerinde aşağıdaki konumlarda bulunur:

#### Windows XP:
- C:\Documents and Settings\<username>\Recent\

#### Windows 7:
- C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\
- C:\Users\<username>\AppData\Roaming\Microsoft\Office\Recent\

#### Windows 10 ve Sonrası:
- C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\
- C:\Users\<username>\AppData\Roaming\Microsoft\Office\Recent\

## Analiz
yukarı da belirtilmiş olan adrese gidilip dosya açılmıştır.
![image](https://github.com/user-attachments/assets/2bb27257-31b7-427e-a06e-5f7c10e9814b)
Açılan dosyada dosyaların Türleri değiştirme tarihleri ve boyutları gözükmektedir. Ve dosyalar çok küçük boyutlardadaır. Bu dosyaları parser ederk gerçek veriye ulaşmaya çalışabilriiz.
bunun için öncelikle dosyaların kopyalayıp başka bir klasörde muhafaza edelim.
Ardından LinkParser aracını kullanarak dosyayı içeri aktaralım.
![image](https://github.com/user-attachments/assets/951948fd-0602-4449-9628-970c5d50e0fc)
LinkParser aracının anlamsız bir şekilde çalışmamasından ötürü başka bir uygulamaya geçiş yaptım. Sanırsam gudubetliğim iş başında :)
bu süreçte Windows File Analysis aracının kullanarak ilgili dosyayaı seçtim ve aşağıdaki görüntüde bilgileiri elde etmiş oldum.
![image](https://github.com/user-attachments/assets/25951380-2c5e-4990-9689-55c4542209f9)
Bu araç sayesinde dosyanın ismi, bulunduğu yol, hangi bilgisayarda olduğu, MAC adresi veya hash değeri gibi pek çok bilgi öğrenilebilir. 
Bu çıkarımlar, adli analizlerde ve değerlendirmelerde oldukça faydalı olabilir.

