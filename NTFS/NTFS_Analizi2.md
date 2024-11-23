# NTFS Analizi

## $MFT (Master File Table)
MFT dosyası içerisinde iki temel öznitelik dosyası bulunmaktadır:

### 1. **$STANDARD_INFORMATION**
- Bir dosya hakkında standart metadata bilgilerini barındırır.
- İçerdiği bilgiler:
  - Dosyanın oluşturulma tarihi
  - Son değiştirilme tarihi
  - Erişim tarihi
  - MFT değerinin son değiştirilme tarihi
- Toplamda 4 zaman damgası içerir.
- **Not:** Bu zaman damgaları kullanıcı tarafından değiştirilebilir.

### 2. **$FILENAME**
- Dosya ve dizinlerin adlarını saklar.
- İçerdiği bilgiler:
  - Dosyanın oluşturulma tarihi
  - Son değiştirilme tarihi
  - Son erişim tarihi
  - MFT değerinin son değiştirilme tarihi
- Toplamda 4 zaman damgası içerir.
- **Not:** Bu zaman damgaları sistem çekirdeği tarafından değiştirilebilir.

**Sonuç olarak:** MFT içerisinde toplamda **8 zaman damgası** bulunmaktadır.

## $LOGFILE
- Sistem çökmesi veya elektrik kesintisi gibi durumlarda dosya sisteminin bozulmasını önlemek için gereklidir.

## $USNJRNL (Update Sequence Number Journal)
- Microsoft, dosya sisteminin güvenilirliğini artırmak için bu kayıt günlük dosyasını eklemiştir.
- **Kullanımı:**
  - Bir sistem güncellemesinden önce ve güncelleme sonrasında kayıt alınır.
  - Eğer sistem çökerse, journal içindeki kayıtlar kullanılarak sistem eski haline döndürülebilir.


# NTFS Konumları

## $MFT
- **Konum:** `C:\$MFT`
- **Kullanım Aracı:** FTK Imager Lite

## $LOGFILE
- **Konum:** `C:\$LOGFILE`
- **Kullanım Aracı:** FTK Imager Lite

## $USNJRNL
- **Konum:** `C:\$Extend\$UsnJrnl`
- **Kullanım Aracı:** FTK Imager Lite


![image](https://github.com/user-attachments/assets/bf5e0aa2-d021-4242-b86b-55ddb3423281)

![image](https://github.com/user-attachments/assets/dbaad996-d703-4c98-9d14-17c0e0cdb22c)


# Analiz

Öncelikle FTK imager üzerinden yukarda belirtilen ilgili konumlara gidilip dposyalar export edilir.

![image](https://github.com/user-attachments/assets/36346132-faef-4091-b9eb-f1f61405b472)

İlgili bu dosyaları çektinden sonra aprser ilemi için ANJP aracını kullanılacaktır. Ayrıca bu tool ayrıştırılan dosyaları rapor formatında bizlere sunabilmektedir.
Gereksiz bir şekilde bende olmadı burayı daha sonra yazacağım.











