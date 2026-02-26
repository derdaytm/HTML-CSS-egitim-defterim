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

### 📚 Konu Akışı
 
**➡️ Sonraki:** [**Metin ve Biçimlendirme**](02-metin-ve-bicimlendirme.md)   
