## HTML

- **HTML (Hyper Text Markup Language)**; web sayfalarının yapısını oluşturan bir işaretleme dilidir.
- **HTML** *tag / element / etiket* olarak adlandırılan yapılardan oluşur.
- Etiketler `< >` arasına yazılır. Genellikle **açılış** ve **kapanış** etiketi şeklindedir.  
  Kapanış etiketlerinde başa `/` işareti gelir.
- HTML dosyalarının uzantısı **`.html`** veya **`.htm`**’dir.
- HTML etiketleri büyük veya küçük harfle yazılabilir; ancak **küçük harf kullanımı** tavsiye edilir.
- Kodların **okunabilirliği artırmak** için girintili ve alt alta yazılması önerilir.
- HTML’de açılan her etiket kapatılmalıdır. Aksi halde kod hatalarına yol açabilir.
- Bazı etiketlerin kapanışı yoktur (boş elementler). İstenirse sonuna `/` eklenebilir (zorunlu değildir).

---

### Standartlar ve Uyumluluk

- Web sayfaları arama motorları tarafından belirli kriterlere göre değerlendirilir ve sayfanın sıralamasını belirler.  
  Hatalı veya tarayıcı uyumsuz kodlar sayfanın algoritmik değerlendirmesini düşürebilir.
- Yazılan kodların **W3C standartlarına** uygunluğu  
  👉 https://validator.w3.org/ adresinden test edilebilir.

---

### Hosting ve Sunucu Bilgisi

- Bir sitenin yayınlanabilmesi için **domain** ve **hosting** gereklidir.
  - **Domain (Alan Adı)**: Kullanıcıların sitenize ulaşmak için tarayıcıya yazdığı isimdir. Genellikle yıllık kiralama usulüyle çalışır.
  - **Hosting (Barındırma)**: Sitenizin resim, içerik, veritabanı ve kod dosyalarının saklandığı, internete bağlı sunucu hizmetidir. Aylık veya yıllık abonelikle çalışır.

---

### Semantik HTML ve SEO

- **Semantik etiketler**, hem insanlar hem de arama motorları tarafından daha kolay anlaşılır.
- Doğru semantik yapı, arama motorlarında daha sağlıklı indekslenmeyi ve dolaylı olarak SEO performansını destekler.
- SEO açısından **`title` etiketi** çok önemlidir.
  - Başlık kısa ve açıklayıcı olmalıdır (ilk **60 karakter** dikkate alınır).
  - Her sayfanın başlığı farklı olmalıdır.

---

### Progressive Enhancement

- Kullanıcılar her koşulda en azından **içeriği okuyabilmelidir**.
- Bu amaçla **Chris Champion’ın “Progressive Enhancement”** yaklaşımı benimsenir:
  1. Önce **HTML** ile içerik oluşturulur.
  2. Ardından **CSS** ile stil eklenir.
  3. Son olarak **JavaScript** ve üçüncü parti eklentiler kullanılır.

---

### Dosya İsimlendirme

- Dosya adlarında:
  - Sadece **küçük harf** kullanılmalıdır.
  - **Türkçe karakter** kullanılmamalıdır.
  - Boşluk yerine `-` tercih edilmelidir. (`_` kullanılabilir ancak `-` daha yaygındır)

---

## Temel Yapı 

```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Temel Sayfa</title>
</head>
<body>
  <h1>Merhaba Dünya</h1>
  <p>Bu, temel HTML yapısının basit bir örneğidir.</p>
</body>
</html>
```

---

## Bazı elementler :

### Bazı HTML Element ve Attribute’ları

- `name="username"` → Form verilerini tanımlamak için elemente isim verir; sadece form gönderiminde kullanılır.  
- `id="header"` → Elementi benzersiz şekilde tanımlar; CSS veya JavaScript ile erişmek için kullanılır.  
- `// Yorum` → Tek satırlık yorum yazmak için kullanılır (genellikle JS veya programlama dillerinde).  
- `<!-- Yorum -->` → HTML’de çok satırlı veya tek satırlık yorum yapmak için kullanılır.  
- `<html lang="tr">` → Sayfanın başlangıcı; dil belirtmek için `lang` kullanılır; sonunda `</html>` ile kapatılır.  
  - `<!DOCTYPE html>` → Sayfanın HTML5 ile yazıldığını belirtir; `<html>`’den önce gelir.  
- `<head>` → Sayfa başlığı, meta bilgiler ve script/link gibi başlık bilgilerini içerir.  
- `<body>` → Ziyaretçiye gösterilen içerik burada yer alır.  
- `<title>` → Tarayıcı sekmesinde görünen sayfa başlığını belirtir.  
- `tabindex="1"` → Elementin tab sırasını belirler; sayfa içinde tab ile gezinmeyi kontrol eder.  
- `accesskey="h"` → Klavye kısayolu atar; örneğin `h` tuşu ile element seçilebilir.  
- `style="color: red; font-size: 16px;"` → Inline CSS uygulanmasını sağlar; elementin stilini belirler.  

> **NOT:**
>
> Bu element ve attribute’lar HTML’in temel yapı taşlarıdır. İleride kullanımlarını anlayacağız.

---

### 📚 Konu Akışı
 
**➡️ Sonraki:** [**Metin ve Biçimlendirme**](02-metin-ve-bicimlendirme.md)   
