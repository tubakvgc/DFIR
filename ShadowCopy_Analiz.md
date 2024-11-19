# Shadow Copy Analizi

Shadow Copy (Gölge Kopya), Windows işletim sistemi tarafından dosya yedekleme ve sürüm kontrolü için kullanılan bir özelliktir. Adli bilişim analizinde Shadow Copy, silinmiş veya değiştirilmiş dosyaların eski sürümlerini incelemek için kritik bir kaynaktır.

## Analiz
Bir bilgisyaarda sadece 64 tane shadow copy barındırılabilir. Aşağıdaki komutu yazarak bilgisayarda daha önceden bulundurulan shadow copy listesini görebiliriz.
- vssadmin list shadows 
![image](https://github.com/user-attachments/assets/d4def017-d615-4069-9f78-351674ed964d)

Resime göre shadow dosyalara ait pek çok bilgilere ulaşılmaktadır. Peki biz bu shadow copy içindeki verileri nasıl bir dizin gibi çıkartabilriiz. İşte bu sorunun cevabı içinde aşağıdaki gibi komut yazarark bir sürücüye export edebiliriz.
![image](https://github.com/user-attachments/assets/83e28de3-a3ff-4153-9a92-3a4df6d63749)

Şimdi belirtlen dizine gidip shadow copy çekmiş olduğu o zamanın verilerine ulaşabiliriz.
![image](https://github.com/user-attachments/assets/feb58f2d-f392-48c9-9c21-4ddb2bde7489)

Bu dosyalar red only oldukları için içlerinde bir değişiklik vs yapılmamaktadır.

Bu işlemi bir imaj içerisinde görebilmek için öncelikle mount edilmesi gerekir.
