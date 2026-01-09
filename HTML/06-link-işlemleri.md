## Link İşlemleri

- `<a>` → Bağlantı (link) oluşturmak için kullanılır. Anchor kelimesinden gelir.
  - `<a>` etiketi içine eklenen metin, görsel veya herhangi bir öğe tıklanabilir olur.
  - `href` alanına zip / rar gibi dosyalar yazılırsa, tarayıcı indirme işlemi başlatır.

### Href Özelliği

- `href="x"` → Bağlantının gideceği konumu belirtir.
  - `#nesne`  → Sayfa içindeki bir konuma gider. (*(id veya name ile sağlanır)* (*Modern HTML'de id tercih edilir*))
  - `sayfa.html` → Aynı sitedeki başka bir HTML sayfasına gider.
    - Aynı klasördeyse direkt yazılabilir.
    - Farklı klasördeyse yol belirtilmelidir.
  - `dosya.zip`/`dosya.rar` → Aynı sitedeki dosyaya gider.
  - `https://site.com` → Başka bir web sitesine yönlendirir.
  - `mailto:mail@example.com` → E-posta bağlantısı oluşturur.

> **Not**:
> Klasör yolu belirtirken `./` kullanmak, dosyanın mevcut proje içinde olduğunu netleştirir ve daha sağlıklı bir yöntemdir.
> `../` kullanarak bir üst klasöre çıkabiliriz.

 ### Title Özelliği

 - `title="x"` → Link üzerine gelindiğinde açıklama gösterir.
 - Kullanıcı deneyimini ve erişilebilirliği destekler.

### Varsayılan Link Görünümü 

- Ziyaret edilmemiş link → Mavi ve altı çizili
- Ziyaret edilmiş link → Mor ve altı çizili
- Aktif (tıklanma anı) link → Kırmızı ve altı çizili

> **Not**:
> Bu görüntüler tarayıcı varsayılanıdır, CSS ile değiştirilebilir.

### Bağlantı Davranışları

- `target="x"` → Bağlantının **nasıl ve nerede açılacağını** belirler.
  - `_self` → Bağlantıyı **aynı sekmede** açar. Varsayılan davranıştır; yazılmasa bile geçerlidir.
  - `_blank` → Bağlantıyı **yeni bir sekmede** açar. Genellikle harici sitelere yönlendirmede kullanılır.
  - `_parent` → Bağlantıyı **üst çerçevede (parent frame)** açar. Frame veya iframe kullanılan yapılarda anlamlıdır.
  - `_top` → Bağlantıyı **tüm çerçeveleri aşarak**, sayfanın **tam gövdesinde** açar. İç içe frame yapılarından çıkmak için kullanılır.

### Rel Özelliği

- `rel="x"` → Bağlantı ile **hedef sayfa arasındaki ilişkiyi** tanımlar.  
  Özellikle **güvenlik**, **SEO** ve **tarayıcı davranışı** açısından önemlidir.
  - `noopener` → `_blank` ile açılan sayfanın, açan sayfaya (`window.opener`) erişmesini engeller. **Güvenlik için önerilir.**
  - `noreferrer` → Hedef sayfaya **referrer (geldiği sayfa) bilgisini göndermez**. Aynı zamanda `noopener` etkisi de sağlar.
  - `nofollow` → Arama motorlarına, bu linki **takip etmemesini** söyler. SEO amaçlı kullanılır.
  - `noopener noreferrer` → En yaygın ve güvenli kullanımdır. Özellikle `target="_blank"` ile birlikte önerilir.

### Download Özelliği 

- `download` → Bağlantıya tıklandığında dosyanın **indirilmeye zorlanmasını** sağlar.
  - `download`  → Dosyayı, sunucu izin veriyorsa **indirir**.
  - `download="dosyaAdi.ext"` → İndirilen dosyanın **kaydedileceği adı** belirler.

> Not:
> - `download` genellikle **aynı origin (aynı site)** dosyalarında çalışır.
> - Harici (başka site) dosyalarda tarayıcı tarafından engellenebilir.

#### Örnek Kullanım

```html
<!-- Sayfa içi link (id ile) -->
<a href="#iletisim" title="İletişim bölümüne git">
  Sayfa içi link
</a>

<!-- Aynı sitede başka sayfa -->
<a href="hakkimizda.html" title="Hakkımızda sayfası">
  Aynı sitede başka sayfa
</a>

<!-- Dosya indirme (download) -->
<a href="./dosyalar/ornek.zip" download="proje-dosyasi.zip" title="Zip dosyasını indir">
  Zip dosyasını indir
</a>

<!-- Harici site + target + rel -->
<a
  href="https://www.google.com"
  target="_blank"
  rel="noopener noreferrer"
  title="Google yeni sekmede açılır"
>
  Harici site (yeni sekme)
</a>

<!-- Mail linki -->
<a href="mailto:mail@example.com" title="E-posta gönder">
  E-posta gönder
</a>

<!-- Frame / üst gövde davranışı -->
<a href="sayfa.html" target="_top" title="Tüm çerçevede açılır">
  Üst gövdede aç (_top)
</a>
```

**Tarayıcı Çıktısı:**

<img width="775" height="129" alt="image" src="https://github.com/user-attachments/assets/88c8e0aa-c7d8-44b5-a565-f2f461aa2ec3" />

---

## Iframe (Sayfa İçinde Sayfa) İşlemleri

- `<iframe>` → Bir web sayfasının **içinde başka bir web sayfası** açmak için kullanılır.
- Genellikle harici içerik (harita, video, dokümantasyon, başka sayfa) göstermek için tercih edilir.
- `src` → Iframe içinde açılacak sayfanın adresini belirtir.
- `title` → Erişilebilirlik için zorunludur.
  - Ekran okuyuculara iframe içeriğinin ne olduğunu açıklar.

### Boyutlandırma

- `width` → Iframe genişliğini belirler.
- `height` → Iframe yüksekliğini belirler.

### Iframe İçinde Link ile Gezinme

- Bir linke tıklandığında sayfanın iframe içinde açılması isteniyorsa:
  - `<iframe>` etiketine name verilmelidir.
  - `<a>` etiketinde `target` değeri, iframe’in `name` değeriyle aynı olmalıdır.

> **Not:**
> Linke tıklandığında sayfa yeni sekmede değil, iframe içinde açılır.
> `target="_blank"` yerine iframe adı kullanılmış olur.

### Önemli Noktalar

- Bazı siteler güvenlik nedeniyle iframe içinde açılmayı engeller.
- Iframe içine alınan sayfa, tarayıcı ve site politikalarına bağlıdır.
- Iframe, SEO açısından sınırlı katkı sağlar; genellikle içerik gömmek için kullanılır.
- Modern projelerde iframe kullanımı kontrollü ve sınırlı olmalıdır.

#### Örnek Kullanım

```html
<iframe
  src=""
  name="iframe_a"
  width="600"
  height="400"
  title="Gezilebilir iframe örneği">
</iframe>

<p>
  <a href="https://www.deydev.com" target="iframe_a">
    deydev.com
  </a>
</p>
```

**Tarayıcı Çıktısı:**

<img width="772" height="491" alt="image" src="https://github.com/user-attachments/assets/29afb9e5-4937-4de4-93d2-6238823f3b24" />

--- 

## `crossorigin` Özelliği

- `crossorigin="x"` → Harici (başka domain) kaynaklara yapılan isteklerde **CORS (Cross-Origin Resource Sharing)** davranışını belirler.
- Genellikle **`script`**, **`img`**, **`video`**, **`audio`**, **`link (font)`** gibi etiketlerde kullanılır.
- `<a>` (anchor) etiketi için **anlamlı değildir**, daha çok kaynak (resource) yüklemede kullanılır.

### Kullanım Değerleri

- `crossorigin="anonymous"`
  - Kimlik bilgisi (**cookie, authorization header**) gönderilmez.
  - Sunucu `Access-Control-Allow-Origin` başlığı ile izin veriyorsa kaynak yüklenir.
  - En yaygın ve güvenli kullanımdır.
  - Font, media ve script dosyalarında sıkça kullanılır.

- `crossorigin="use-credentials"`
  - İstekle birlikte **cookie**, **authorization header** gibi kimlik bilgileri gönderilir.
  - Sunucu tarafında:
    - `Access-Control-Allow-Credentials: true`
    - Belirli bir origin tanımı gerekir (`*` kullanılamaz).
  - Genellikle **API**, **kimlik doğrulama**, **özel kullanıcı verileri** için kullanılır.

> **Not:**
> `crossorigin` CORS’u tek başına çözmez; sunucu tarafı ayarları zorunludur.

---

## `rel` Özelliği

- `rel="x"` → Mevcut sayfa ile hedef kaynak arasındaki **ilişki türünü** tanımlar.
- En çok `<a>` ve `<link>` etiketlerinde kullanılır.
- **SEO**, **güvenlik**, **tarayıcı davranışı** açısından önemlidir.

### Yaygın `rel` Değerleri

- `noopener`
  - Yeni açılan sayfanın (`_blank`) açan sayfaya erişmesini engeller.
  - Güvenlik için önerilir.

- `noreferrer`
  - Hedef sayfaya **referrer (geldiği sayfa)** bilgisini göndermez.
  - Aynı zamanda `noopener` etkisi gösterir.

- `nofollow`
  - Arama motorlarına bu linki **takip etmemesini** söyler.
  - SEO amaçlı kullanılır.

- `alternate`
  - Sayfanın **alternatif bir versiyonu** olduğunu belirtir.
  - Örnek: farklı dil, farklı format (RSS, PDF).

- `stylesheet`
  - Harici bir CSS dosyasını belirtir.
  - `<link>` etiketiyle kullanılır.

> **Önemli Düzeltme:**
> `rel` yalnızca “başka bir sayfanın alternatifi” anlamına gelmez; **ilişki türünü** belirtir.

---

### `rev` Özelliği (⚠️ Eski / Kullanılmıyor)

- `rev` → `rel`’in ters ilişkiyi tanımlayan eski halidir.
- HTML5 ile **kaldırılmıştır / önerilmez**.
- Modern HTML’de **kullanılmamalıdır**.

> **Not:**
> `rev` yerine her zaman `rel` kullanılmalıdır.

---

### Kısa Özet

- `crossorigin` → Harici kaynaklarda **CORS davranışını** belirler
- `rel` → Sayfalar/kaynaklar arasındaki **ilişkiyi** tanımlar
- `rev` → **Deprecated (kullanılmıyor)**

> Modern HTML’de güvenlik, erişilebilirlik ve SEO için  
> `rel` ve `crossorigin` doğru ve bilinçli kullanılmalıdır.

---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Tablo ve Liste İşlemleri**](05-tablo-ve-liste-işlemleri.md)   
**➡️ Sonraki:** [**Form İşlemleri**](07-form-işlemleri.md)
