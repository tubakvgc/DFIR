# Prefetch Analizi
Prefetch dosyaları, Windows işletim sistemi tarafından sık kullanılan uygulamaların başlatılma sürelerini optimize etmek için oluşturulur. Adli bilişim analizinde Prefetch dosyaları, bir sistemde çalıştırılan uygulamaların geçmişini izlemek için değerli bilgiler sağlar.

## Prefetch Dosyalarının Konumları
Prefetch dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- C:\Windows\Prefetch
  
#### Windows 7:
- C:\Windows\Prefetch

#### Windows 10 ve Sonrası:
- C:\Windows\Prefetch

## Analiz
Yukarı da belirtilmiş olan adrese gidilip klasör açılmıştır.
![image](https://github.com/user-attachments/assets/d93e505c-34fc-4ba0-af41-2f72cd7e9e50)

Görüldüğü üzere, Prefetch dosyalarının uzantıları .pf şeklindedir. WinPrefetchView.exe aracını aşağıdaki gibi çalıştırdığınızda, bilgisayardaki tüm Prefetch dosyalarını görüntüleyebilirsiniz. Bu araç, her bir Prefetch dosyasına ait detayları (örneğin, çalıştırılan uygulamalar ve disk erişimleri) listeler. Ayrıca, Prefetch dosyalarının alt kısmında ilgili DLL dosyaları da görüntülenmektedir.

![image](https://github.com/user-attachments/assets/c909dda7-3673-463c-86c8-4d2b65105a88)

Attribute Changer 9 aracı kullanılarak, Prefetch dosyalarının değiştirilme tarihleriyle oynanabilir ve bu yöntem, anti-adli bilişim (anti-forensic) amaçlar için kullanılabilir. Bu araç sayesinde dosyaların oluşturulma, değiştirilme ve erişilme tarihleri manipüle edilerek gerçek zaman çizelgeleri yanıltılabilir.






















