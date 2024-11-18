# Jump Lists Analizi

Jump Lists (Sıçrama Listeleri), Windows işletim sistemlerinde kullanıcıların en son eriştiği dosya ve programların izini sürmek için kullanılan bir özellik olup, adli bilişim analizlerinde oldukça değerlidir. Jump Lists, kullanıcı davranışları ve dosya erişimi hakkında bilgi edinmek için sıkça incelenir. Kullanıcıların en çok okunan, erişilen veya ziyaret edilen dökümanlara resimlere, müziklere, vb. şeylere daha hızlı erişmelerine imkan tanır.


## Jump Lists Dosyalarının Konumları
Jump Lists dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- Yok
  
#### Windows 7:
- AutomaticDestinations:
C:\Users\[UserName]\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations
- CustomDestinations:
C:\Users\[UserName]\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations

#### Windows 10 ve Sonrası:
- AutomaticDestinations:
C:\Users\[UserName]\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations
- CustomDestinations:
C:\Users\[UserName]\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations

## Analiz
Yukarı da belirtilmiş olan adrese gidelim ve aşağıdaki gibi automativ ve custom Destinationları görüntülüyoruz.
![image](https://github.com/user-attachments/assets/09559b26-8d80-4426-ad8e-b312c2e52693)

Ardından hepsinin içine girip gözlemleyelim;
![image](https://github.com/user-attachments/assets/e8cdea7c-695d-43de-ad12-88a4d4cdb18b)
Burada verilen app id numaraları ile internette ya da verilen liste üzerinde araştırma yapılıp hangi uygulamaya ait olduğunu bilgisini anlayabilriz.

CustomDestinationda ise aşağıdaki gibi dosyalar vardır.
![image](https://github.com/user-attachments/assets/694fd255-8baa-4117-98cb-d82fddd5e527)

JumpListsView.exe aracı kullanrak anlık olarak tüm jumplistleri göstermektedir.
![image](https://github.com/user-attachments/assets/952b61f8-329f-4561-b6a8-9685af904675)

Silinmiş olan dosyaaları bile jumplist ile edlde eddebilriiz. Bundan dolayı adlli bilişim açısından çok değerlidir.

#### Çıkarım
JumpListsView aracı, dosya adı, tam yol, kayıt zamanı, oluşturulma zamanı, değiştirilme zamanı, erişim zamanı, dosya boyutu, dosya uzantısı, bilgisayar adı, uygulama kimliği ve Jump Lists dosya adı gibi bilgileri elde ederek kullanıcı aktivitelerini, dosya ve uygulama erişimlerini, olay zaman çizelgesini ve şüpheli faaliyetleri tespit etmek için adli bilişim analizlerinde kullanılır.
