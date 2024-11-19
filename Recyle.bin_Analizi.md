# Recycle Bin Analizi

Recycle Bin ($Recycle.Bin) klasörü, çöp kutusuna atılmış dosyalardır. Windows işletim sisteminde silinen dosyaların geçici olarak saklandığı bir alandır. Bu alan, adli bilişim analizlerinde oldukça değerlidir çünkü kullanıcı tarafından silinen dosyalara dair önemli bilgiler içerir.

## Recycle Bin Dosyalarının Konumları
Recycle Bin dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- C:\RECYCLER
  
#### Windows 7:
- C:$Recycle.Bin

#### Windows 10 ve Sonrası:
- C:$Recycle.Bin

## Analiz
Yukarı da belirtilmiş olan adrese gidilip dosya açılmıştır.
![image](https://github.com/user-attachments/assets/b685d2e1-5ad7-419e-ad56-bf6bf04ea2f4)

Her kullanıcının Recycle Bin dosyası, o kullanıcıya ait SID numarası klasöründe depolanır. Buradaki SID numaralarının bulunma nedeni budur.

Şimdi cmd yönetiic olarak açalım ve aşağıdaki komutları yazalım
![image](https://github.com/user-attachments/assets/a6c5244c-0ed1-41d2-a4d2-5d2cfb84c65e)

- C:\$Recycle.Bin>dir /a --> Bu komut, $Recycle.Bin klasöründeki tüm dosyaları ve SID numaralarına ait alt klasörleri gösterir. Ancak, SID numaralarının hangi kullanıcıya ait olduğu bu aşamada bilinmemektedir.
- C:\$Recycle.Bin>wmic useraccount get name,sid --> Eğer bilgisayarınız domainde değilse ve kişisel bir bilgisayar kullanıyorsanız, SID numaralarını kullanıcı adlarıyla eşleştirmek için bu komutu kullanabilirsiniz
- C:\$Recycle.Bin>whoami /user --> içinde bulunduğum kullanıcının sid numarası için bu komutu yazıyoruz ve cd ile o dosyaya içine giriyoruz.
- C:\$Recycle.Bin\S-1-5-21-4281717408-3789806728-727355090-1001>dir/a --> ardından bu sid nuamrası içindeki dosyaları görüntüleyip bakıyoruz ve anlamsız isimler bulunmakta sadece uzantıları görünmektedir.

![image](https://github.com/user-attachments/assets/38146ed0-9861-464a-9e46-9d59097a7ab1)

copy $* "C:\Users\Tuba Kavgacı\Desktop\recylebin"
dosyaları yukardaki komutu yazarark bir dizine export ediyoruz ve aşağıdaki gibi klasörde dosyaları görüntüleyebilriz.
![image](https://github.com/user-attachments/assets/6d29628f-ccbb-4d30-aec2-3c622508bda9)

Şimdi $I_Parse aracını kullanarak aşağıdaki gibi önce kaynağı sonrada hedef yolunu belirttik ve 7 tane parser olduğu uayrısını aldık.
![image](https://github.com/user-attachments/assets/b6c2e8d2-f700-498f-a5f5-f285ceee3182)

Ve output çıktısına giderek aşağüıdaki gibi verilerin delete tarihi, dosya yolu ve ismi, size ve vaersion bilgilerine erişmiş olduk.
![image](https://github.com/user-attachments/assets/6ea9381e-4e07-43b7-a47e-65fa4ba5674c)
