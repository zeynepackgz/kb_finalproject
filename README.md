# 📊 Paşabahçe Marka Analizi - Power BI Projesi

## 📝 Proje Açıklaması
Bu Power BI projesi, Paşabahçe markasının kullanıcı, adres, sipariş ve ürün verileri üzerinden analiz edilmesini hedeflemektedir. Veri modelleme, DAX hesaplamaları ve görselleştirme teknikleri kullanılarak satış, müşteri, kategori ve bölge odaklı analizler gerçekleştirilmiştir.

---

## 📹 Proje Tanıtım Videosu

[📺 YouTube'da İzle](https://youtu.be/Akwc9e0JDZ8)

---

## 📁 Veri Setleri

- **kullanicilar.csv** → Kullanıcı bilgileri (ID, isim, cinsiyet, doğum tarihi, kayıt tarihi)
- **adres.csv** → Adres bilgileri (City, District, ID)
- **orders.csv** → Sipariş bilgileri (ID, UserID, Date, TotalPrice, AddressID)
- **orderdetail.csv** → Sipariş detayları (OrderID, ItemID, Quantity)
- **items.csv** → Ürün bilgileri (ID, ItemName, Category fields)
- **bölgeler.csv** → Şehir-bölge eşleşmeleri

---

## 🔗 Veri Modeli İlişkileri

- `KULLANICILAR[ID]` → `SIPARIS[USERID]`
- `SIPARIS[ID]` → `SIPARISDETAY[ORDERID]`
- `SIPARISDETAY[ITEMID]` → `URUNLER[ID]`
- `SIPARIS[ADDRESSID]` → `ADRES[ID]`
- `ADRES[CITY]` → `BÖLGELER[İL]`

---

## 🧮 DAX Hesaplamaları

**Yaş (Yeni Sütun):**
DAX
AGE = DATEDIFF(KULLANICILAR[BIRTHDATE], KULLANICILAR[CREATEDDATE], YEAR)

Yaş Grubu (Koşullu Sütun):
YAŞGRUBU = 
SWITCH(
    TRUE(),
    AGE <= 20, "GENÇ (0-20)",
    AGE <= 35, "YETİŞKİN (21-35)",
    AGE <= 55, "ORTA YAŞ (36-55)",
    "YAŞLI (55+)"
)

---

## 📊 Rapor Sayfaları ve İçeriği
1. Giriş Sayfası
Basit butonlar ile rapor bölümlerine yönlendirme.

2. Özet Sayfası
Toplam sipariş adedi, müşteri sayısı, toplam ciro gibi KPI kartları.

Saatlik satış trendi, sipariş durumu dağılımı.

Ortalama sipariş başına ciro, adet gibi metrikler.

3. Müşteri Perspektifi
Cinsiyet dağılımı (Treemap veya pasta grafik)

Yaş grubu bazlı satış (Bar grafik)

Bölge bazlı müşteri sayısı

İstanbul bazlı en çok ciro yapan ilk 10 müşteri (Tablo)

4. Kategori Perspektifi
Ana, üst, alt ve en alt kategorilere göre ciro dağılımı

İçecekler ana kategorisi bazında kıyaslama

İstanbul’daki genç (0–20 yaş) müşterilerin toplam cirosunun kategorilere göre dağılımı (Ağaç Haritası)

## 🧠 Analitik Sorgular
İstanbul’daki genç yaş grubunun alışveriş eğilimleri nelerdir?

Hangi bölgelerde müşteri yoğunluğu daha fazladır?

Hangi yaş grubu, hangi kategoride daha çok harcama yapmaktadır?

Yeni oluşturulan "İçecekler" kategorisi toplam ciroda ne kadar yer tutmaktadır?

## 🧰 Kullanılan Araçlar ve Teknolojiler
Microsoft Power BI

DAX (Data Analysis Expressions)

Power Query

CSV veri dosyaları

📌 Proje Amacı
Bu proje, Paşabahçe markasının müşteri kitlesini daha iyi anlamasına, yaş, cinsiyet, şehir gibi demografik özelliklere göre satış analizleri yapmasına ve ürün kategorilerindeki performansı değerlendirmesine olanak sağlamaktadır.
