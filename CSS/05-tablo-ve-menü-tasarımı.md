## Tablolar ve Menü Tasarımı

Tablo ve menü tasarımına başlamadan önce bilmemiz gereken temel mantık:

### 1. Tabloda Yazı ile İlgili Özellikler
- Tablodaki **metinler**, normal metin biçimlendirmesi gibi stil verilebilir.  
- Yani **font-family, font-size, font-weight, text-align, color** gibi özellikler kullanılabilir.
- [Metin biçimlendirme kısmına geri dönmek için tıklayabilirsiniz.](03-metinlerin-biçimlendirmesi.md)

### 2. Tabloda Kutu ile İlgili Özellikler
- Tablodaki hücreler (`<td>` veya `<th>`) birer **kutu** gibi düşünülebilir.  
- Bu nedenle **kutu modeli** özellikleri uygulanabilir:  
  - `padding` → Hücre içindeki boşluk  
  - `border` → Hücre kenarlıkları  
  - `margin` → Hücreler arasında boşluk (daha çok tablo çevresinde)  
  - `background-color` → Hücre arka plan rengi
- [Kutu modeli kısmına geri dönmek için tıklayabilirsiniz.](06-sayfa-düzeni.md)

---

## Tablolarda Tek Çizgi Kullanımı

Tabloların kenarlıkları bazen **çift çizgi** gibi görünebilir.  
Bunu önlemek ve **tek çizgi görünümü** elde etmek için `border-collapse` özelliği kullanılır.

### Kullanım

```css
table {
  border-collapse: collapse; /* Çift çizgileri tek çizgi yapar */
}
```

---

## Listelerde Metin ve Kutu Özellikleri

Listeler (`<ul>`, `<ol>`, `<li>`) de tablolar gibi **iki açıdan stil verilebilir**:  

### 1. Metin Biçimlendirme
- Listelerdeki metinler normal yazı stilinde olduğu gibi biçimlendirilebilir:  
  - `font-family` → Yazı tipi  
  - `font-size` → Yazı boyutu  
  - `font-weight` → Kalınlık  
  - `color` → Yazı rengi  
  - `text-align` → Hizalama
- [Metin biçimlendirme kısmına geri dönmek için tıklayabilirsiniz.](03-metinlerin-biçimlendirmesi.md)

### 2. Kutu Modeli Özellikleri
- Listelerin kutuları veya listelerdeki öğeler (`<li>`) **kutu modeli** özellikleriyle şekillendirilebilir:  
  - `padding` → Liste öğesi iç boşluğu  
  - `margin` → Liste öğesi dış boşluğu  
  - `border` → Kenarlık ekleme  
  - `background-color` → Arka plan rengi  
- [Kutu modeli kısmına geri dönmek için tıklayabilirsiniz.](06-sayfa-düzeni.md)

---

## Listeleri Yatay Yapma

Varsayılan olarak listeler dikey (alt alta) görüntülenir.  
Eğer **liste öğelerini yatay** yani yan yana göstermek istersek `float: left;` kullanılır.

### Örnek CSS

```css
ul li {
  float: left;      /* Liste öğelerini yan yana dizer */
  margin-right: 15px; /* Öğeler arası boşluk */
  list-style: none;   /* Madde işaretlerini kaldırır */
}
```

### Önemli Not: Clearfix

Not: Bu yöntemde, liste kapsayıcısının (`<ul>` veya `<ol>`) sonunda **clearfix** uygulanması önerilir.  
Aksi takdirde, kapsayıcının yüksekliği **float uygulanan öğeler nedeniyle doğru hesaplanmayabilir**.

**Detaylı Açıklama**

- `float: left;` veya `float: right;` kullandığımızda, elemanlar normal akıştan çıkar.  
- Bu durumda **ebeveyn kapsayıcı** (`<ul>` veya `<ol>`) **yükseklik olarak sıfır gibi davranabilir**, yani kapsayıcı sadece içindeki "normal akışta olan" öğeleri görür.  
- **Çözüm:** Clearfix uygulamak. Böylece kapsayıcı, içindeki floated elemanların yüksekliğini de kapsar.

#### Clearfix Örneği:
HTML Dosyası :
```html
<ul class="clearfix">
  <li>Öğe 1</li>
  <li>Öğe 2</li>
  <li>Öğe 3</li>
</ul>
```
CSS Dosyası :
```css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

---

## Listelerde Madde İşaretlerini Belirleme

Listelerde varsayılan olarak `list-style-type` kullanılarak **madde işaretleri veya numaralandırma tipi** belirlenir.  

### Değerler ve Anlamları

| Değer | Açıklama |
|-------|----------|
| `none` | Boş, madde işareti yok |
| `disc` | Daire dolu |
| `circle` | Daire boş (çember) |
| `square` | Kare |
| `decimal` | Numara (1, 2, 3…) |
| `lower-alpha` | Küçük harfli (a, b, c…) |
| `lower-greek` | Yunanca küçük harf (α, β, γ…) |
| `lower-latin` | Latince küçük harf (a, b, c…) |
| `lower-roman` | Küçük Roma rakamı (i, ii, iii…) |
| `upper-alpha` | Büyük harfli (A, B, C…) |
| `upper-greek` | Yunanca büyük harf (Α, Β, Γ…) |
| `upper-latin` | Latince büyük harf (A, B, C…) |
| `upper-roman` | Büyük Roma rakamı (I, II, III…) |
| `url("dosyakonumu")` | Madde yerine resim görüntülenir |

### Örnek Kullanım

```css
ul.ornek1 {
  list-style-type: square; /* Madde işareti kare */
}

ol.ornek2 {
  list-style-type: upper-roman; /* Büyük Roma rakamı */
}

ul.ornek3 {
  list-style-type: none; /* Madde işareti yok */
}

ul.ornek4 {
  list-style-image: url("img/madde.png"); /* Resim ile madde */
}
```

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Kutu Modeli**](04-kutu-modeli.md)   
**➡️ Sonraki:** [**Sayfa Düzeni**](06-sayfa-düzeni.md)
