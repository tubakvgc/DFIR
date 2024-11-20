# AutoRun Analizi

AutoRun, Windows işletim sisteminde, belirli bir medya (örneğin, CD, DVD, USB bellek) veya uygulama bağlandığında otomatik olarak belirli bir programı çalıştırmak veya bir komutu yürütmek için kullanılan bir özelliktir. İlk olarak Windows 95 ile tanıtılan AutoRun, kullanıcı deneyimini kolaylaştırmak amacıyla geliştirilmiştir. AutoRun, genellikle taşınabilir medya bağlandığında otomatik olarak bir kurulum programı başlatmak için kullanılır.

## Analiz
Bu durum için AutoRun aracını kullanacağız.
![image](https://github.com/user-attachments/assets/88e4586e-2351-4e93-840f-c3801f86917f)

Burda bizim için önemli olan iki kısım vardır;
1. Logon
2. Scheduled Tasks
kısımlarıdır.

Logon bölümü, bilgisayar açıldığında otomatik olarak çalıştırılan tüm uygulamalar ve komutlar sıralanır. Potansiyel kötü amaçlı yazılımlar, bu listeye eklenmişse, sistemin her açılışında otomatik olarak çalıştırılabilir.

![image](https://github.com/user-attachments/assets/86bbb75b-7a59-4b3c-bc24-618bfcddd93d)

Scheduled Tasks bölümü, bilgisayarda gelecekteki tarihlerde çalışacak olan programların ve işlemlerin listesine erişim sağlar. Bu, zamanlanmış bir şekilde başlatılacak herhangi bir işlem hakkında bilgi verir.
Bu, kötü amaçlı yazılımların zamanlanmış bir şekilde başlatılmasını tespit etmek için faydalıdır. Malware, doğrudan çalıştırılmak yerine belirli bir zaman diliminde veya belirli bir olayda çalışacak şekilde ayarlanmış olabilir.

![image](https://github.com/user-attachments/assets/0d7f000d-91d7-43b5-9293-0b2311a3c5b2)

Anlık olarak uygulamaları sağ tıklayıp "Check VirusTotal" diyerek, bu dosyaların güvenli olup olmadığını kontrol edebilirsiniz. Bu, dosyanın kötü amaçlı olup olmadığını belirlemenin hızlı bir yoludur.

![image](https://github.com/user-attachments/assets/389e26f8-f503-4ba5-bef3-bc928bd57369)

AutoRun ve Scheduled Tasks analizleri, sistemdeki otomatik çalıştırma özelliklerinin güvenliğini değerlendirmek ve kötü amaçlı yazılımları tespit etmek için önemli araçlardır. Logon ve Scheduled Tasks bölümlerinde yapılan analizler, malware'in başlangıcını ve zamanlanmış aktivitelerini tespit etmekte yardımcı olabilir. Ayrıca, VirusTotal ile yapılan taramalar, dosyaların güvenliğini hızlıca kontrol etmek için etkili bir yöntemdir.





