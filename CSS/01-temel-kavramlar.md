# CSS (Cascading Style Sheets)
- CSS, HTML elemanlarının görünümünü ve düzenini kontrol etmek için kullanılır.
- Temel olarak **3 parçadan oluşur :**
    1. **Selector (Seçici)** : Stil uygulanacak HTML elemanını belirtir.
    2. **Property (Özellik)** : HTML elemanına uygulanacak stil özelliğini belirtir.
    3. **Value (Değer)** : Property'nin alacağı **değeri** belirtir.

> **NOT :**
>
> `//` = CSS'te tek satırlık açıklama yapmayı sağlar.   
> `/* x */` = CSS'te çok satırlı açıklama yapmayı sağlar. 

> **NOT :**
>
> Diğer dillerde olduğu gibi CSS'tede **anlaşılır yazmak önemlidir**. Bu yüzden stil kurallarını **bloklar halinde** yazmak gerekir.

Temel Yapı :
  ```css
/* Tüm paragrafların yazısı mavi ve 16px olsun */
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır */
p {
  color: blue;       /* Property: color, Value: blue */
  font-size: 16px;   /* Property: font-size, Value: 16px */
  margin: 10px;      /* Property: margin, Value: 10px */
  padding: 5px;      /* Property: padding, Value: 5px */
}
  ```

- Buradaki yapıyı incelediğimiz de :
  1. Selectordan sonra süslü parantez açılır ve komutlar süslü parantez içine yazılır.
  2. Property ve value arasında `:` konulur.
  3. Property'ler arasına `;` konulur.

> **ÖZET**
>
> CSS = Selector (hangi eleman) + property (hangi özellik) + value (değer)

---

## CSS Dosyasını / Dosyalarını HTML'e Bağlama
### En Yaygın Yöntem
```html
<link rel="stylesheet" type="text/css" href="dosyakonumu.css">
```
- HTML sayfasının `head` kısmına eklenir.
- `rel="stylesheet"` = Stil dosyası olduğunu belirtir.
- `type ="text/css` = Dosya türünü belirtir. (Çoğu modern tarayıcıda opsiyonel)
- `href="dosyakonumu.css` = CSS dosyasının konumunu belirtir.

> **NOT:**
>
> `./` = Bulunduğu klasör anlamına gelir.
> `../` = Bir üst klasör anlamına gelir.

### Alternatif Yöntem (tercih edilmez)
```html
<style type="text/css">
    @import "stil_dosyasi.css";
</style>
```

- Bu yöntem CSS'i HTML içinde import eder.
- Performans açısından tavsiye edilmez.
- `<style type="text/css">`
  - HTML sayfasının `head` kısmına yazılır.
  - `type="text/css"` = Tarayıcıya buranın CSS olduğunu belirtir. (HTML5'te opsiyonel)
- `@import "dosyakonumu.css"` = Başka bir CSS dosyasını bu sayfaya ekler. 

---

## Birden Fazla CSS Dosyası Kullanma
- Farklı alanlar için ayrı dosyalar oluşturulabilir :
  - menu.css, icerik.css, link.css
  1. Yöntem : 
     ```html
     <link rel="stylesheet" type="text/css" href="menu.css">
     <link rel="stylesheet" type="text/css" href="icerik.css">
     <link rel="stylesheet" type="text/css" href="link.css">
     ```
  2. yöntem (tercih edilmez) :
     - Bu dosyaları **ana stil dosyası** (stil.css) içinde toplamak ve ana dosyayı HTML'e bağlamak.
    `stil.css` dosyası :
     ```css
      @import url("menu.css");
      @import url("icerik.css");
      @import "link.css";
     ```
     `html` dosyası :
     ```html
      <link rel="stylesheet" href="stil.css">
     ```

---

## çoklu CSS Tema Kullanımı ve Default Tema Belirleme
- Eğer bir web sayfasında birden fazla CSS teması varsa, hangi temanın varsayılan (default) olarak yükleneceğini meta etiketi ile belirleyebiliriz.
Örnek Kullanım :
```html
<!-- Default tema belirleme -->
<meta http-equiv="Default-Style" content="mavi">

<!-- CSS dosyaları -->
<link rel="stylesheet" href="mavi-tema.css" type="text/css" title="mavi">
<link rel="stylesheet" href="kirmizi-tema.css" type="text/css" title="kırmızı">
```

- `<meta http-equiv="Default-Style" content="mavi">`
  - Sayfanın açıldığında hangi temanın varsayılan olarak yükleneceğini belirtir.
  - `content` değerine, `<link>` etiketlerinde verdiğimiz `title` isimlerinden birini yazmalıyız.
- `title="mavi"` ve `title="kırmızı"`
  - CSS dosyalarına isim vermek için kullanılır.
  - Bu isimler, kullanıcı veya script tarafından temayı değiştirmek için de kullanılabilir.

> **NOT :**
>
> Bu yöntemle sayfada birden fazla tema barındırabiliriz ve default tema meta etiketi ile kontrol edilir.

---

## CSS Ölçü Birimleri
- **px (piksel)
  - Sabit birimdir, ekran çözünürlüğüne göre değişmez.
  - Mobil cihazlarda farklı çözünürlüklerde ölçeklenmediği için önerilmez.
- **em**
  -  Göreli birimdir; bir elementin font-size değerine göre hesaplanır.
  -  Responsive tasarım için çok uygundur.
- **ex**
  - Bir elementin küçük harfi x karakterinin yüksekliğine göre hesaplanır.
  - Font tabanlı ölçüm için kullanılır, responsive için em kadar yaygın değildir.
- **%**
  - Parent (ebeveyn) elementin boyutuna göre ayarlanır.
  - Responsive ve mobil tasarımlarda çok tercih edilir.
- **in (inç)**
  - Fiziksel ölçü birimidir.
  - Ekran boyutuna göre değişmediği için web tasarımında genellikle kullanılmaz.
- **cm (santimetre)** ve **mm (milimetre)**
  - Fiziksel ölçü birimidir.
  - Web sayfasında kullanımı sınırlıdır, mobil uyumlu değildir.
- **pt (point / puan)**
  - Baskı ölçüsü olarak kullanılır (1pt = 1/72 inç).
  - Dijital ekranlarda kullanımı yaygın değildir, mobil uyumluluk için önerilmez.
- **auto**
  - Tarayıcıya elementin boyutunu otomatik hesaplamasını söyler.
  - Responsive tasarımda sık kullanılan bir yöntemdir.

> **Not **
>
> Mobil uyumluluk ve responsive tasarım için em ve % birimleri öncelikli tercih olmalıdır.

| Ölçü Birimi | Kullanım Alanı | Ne Zaman Tercih Edilir? | Notlar |
|-------------|----------------|------------------------|--------|
| **em**      | Font boyutu, padding, margin, küçük UI elemanları | Font’a göre ölçeklenmesini istediğinizde (yazı içeren butonlar, küçük kutular) | Responsive tasarım için uygundur; parent boyutuna bağlı değildir. |
| **%**       | Genişlik, yükseklik, container boyutları | Ebeveyn elementin boyutuna göre orantı gerektiğinde (layout blokları, grid elemanları) | Font ölçüsü yerine parent ölçüsüne göre ölçeklenir. |
| **auto**    | Genişlik, yükseklik, margin, ortalama | Elementin doğal boyutunu bırakmak veya otomatik ortalamak istediğinizde (margin:auto ile ortalama) | Tarayıcı boyutu hesaplar; responsive için kullanışlıdır ama ölçü vermek gerekmez. |

> ÖZET
>
> - em = Font bazlı ayarlarda
> - % = Layout ve blok boyutlarında
> - auto = Tarayıcıya bırakmak veya ortalamak için

---

## Önemli Noktalar
- CSS kodlarını **açıklama satırları ile gruplamak**, kodun okunabilirliğini ve bakımını kolaylaştırır.  
  Örnek: 
  ```css
  /* HEADER STİLİ */
  header {
      background-color: #333;
      color: #fff;
  }

  /* NAV STİLİ */
   nav a {
      color: #fff;            /* Menü linkleri beyaz */
      text-decoration: none;  /* Alt çizgi kaldırılır */
      margin: 0 15px;         /* Linkler arası boşluk */
      font-weight: bold;      /* Kalın yazı */
  }

  nav a:hover {
      color: #f39c12;         /* Üzerine gelince turuncu olur */
  }
  ```

- CSS dosyanızı [**W3C CSS Validation Service**](https://jigsaw.w3.org/css-validator/) üzerinden kontrol edebilirsiniz. Amaç kodunuzun standartlara uygun olup olmadığını ve tarayıcı uyumluluğunu test etmek.

---
### 📚 Konu Akışı

**➡️ Sonraki:** [**Seçici İşlemleri**](02-seçici-işlemleri.md)
