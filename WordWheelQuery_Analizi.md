# WordWheelQuery Analizi

WordWheelQuery, Windows işletim sisteminde, özellikle Windows Arama (Windows Search) özelliği tarafından kullanıcıların gerçekleştirdiği aramaların geçmişini saklayan bir kayıt mekanizmasıdır. Bu mekanizma, Windows'un kullanıcı deneyimini geliştirmek için kullanıcının önceki aramalarını hatırlamasına olanak tanır. Kayıtlar, genellikle arama çubuğu veya Dosya Gezgini (File Explorer) üzerinde yapılan sorgularla ilgilidir.

## WordWheelQuery Dosyalarının Konumları
WordWheelQuery dosyası aşağıdaki konumda bulunur:

#### Windows XP:
- Windows XP'de WordWheelQuery özelliği bulunmamaktadır.

  
#### Windows 7:
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery

#### Windows 10 ve Sonrası:
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery

## Analiz
İlgili dizine giderek aşağıdaki gibi kayıtları görüntüleyebiliriz. Registry üzerinden WordWheelQuery anahtarındaki değerleri tıklayarak yapılan aramaları inceleyebiliriz:

![image](https://github.com/user-attachments/assets/f1e1f054-0bd4-4b90-996e-3e2b31b90af2)

WordWheelQuery üzerine yeni bir kayıt eklemek için arama çubuğunda yeni bir sorgu yapabilirsiniz. Yapılan sorgular otomatik olarak bu dizinde saklanır:

![image](https://github.com/user-attachments/assets/a3a75950-75b7-4afe-954d-da4dd4e99bf0)

FTK ile Ntuser dosyalarını export edip RegRipper aracı ile parser ettim.

![image](https://github.com/user-attachments/assets/622e0652-4494-4482-803e-ae0508f2d237)

RegRipper aracının oluşturduğu parser çıktısı bir metin dosyasıdır. Bu dosyayı açarak WordWheelQuery verilerine ulaşabilirsiniz. Aşağıda örnek bir parser çıktısı görüntülenmiştir:

![image](https://github.com/user-attachments/assets/43949336-a907-4471-957d-82cb5394f878)
