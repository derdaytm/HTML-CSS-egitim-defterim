 ### Font-Family Özelliği
- `font-family: x, y, z;` → Bir elementin yazı tipini belirler.
- Tarayıcı, listedeki yazı tiplerini **sırayla kontrol eder**.
- Örneğin: Eğer `x` tarayıcıda yüklüyse `x` kullanılır, yoksa `y`, sonra `z` devreye girer.
- Eğer yazı tipi **birden fazla kelime içeriyorsa**, tırnak içine alınmalıdır:

**Örnek Kullanım :**
```css
p {
    font-family: "Times New Roman", Arial, sans-serif;
}
```

- Modern CSS sayesinde, web sayfalarında **her font sorunsuz şekilde uygulanabilir**.
- Türkçe karakterleri doğru göstermek için, **Google Fonts** veya benzeri servislerden font eklerken HTML `<head>` kısmına bu kod eklenir:
`<link href="https://fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext"
      rel="stylesheet" type="text/css">`

> **NOT :**
>
> Font eklerken mutlaka bir **yedek font listesi** belirleyin, böylece kullanıcıların cihazında ana font yoksa bile diğer fontlar devreye girer.
> [Buraya tıklayarak](https://fonts.google.com/) yazı tipi seçebilirsiniz.

---

### Color Özelliği
- `color: x`; → Bir elementin **yazı rengini** belirler.
- `x` yerine **renk adı, hex kodu (#rrggbb)** veya **RGB değeri (rgb(r, g, b))** kullanılabilir.

**Örnek Kullanım :**
```css
/* Renk adı ile */
p {
    color: red;
}

/* Hex kodu ile */
h1 {
    color: #1a73e8;
}

/* RGB ile */
span {
    color: rgb(255, 165, 0); /* turuncu */
}
```

> **NOT :**
>
> Google üzerinden renklerin hex ve RGB kodlarına ulaşabilirsiniz.

- Modern tarayıcıların hepsi bu üç yöntemi de destekler.
- **İpucu:** RGB yerine RGBA kullanarak **şeffaflık (opacity)** da ekleyebilirsiniz:

**Örnek Kullanım :**
```css
div {
    color: rgba(0, 128, 0, 0.7); /* yarı saydam yeşil */
}
```

> **NOT : **
>
> Renk seçerken kontrastı göz önünde bulundurun; özellikle metin arka planla okunabilir olmalı.

---

### Font-Size Özelliği
- `font-size: x;` → Bir elementin yazı boyutunu belirler.
- `x` yerine anahtar kelime, px, em, `%** gibi birimler kullanılabilir.
- Örnek anahtar kelimeler: `smaller`, `small`, `medium`, `large`, `larger`
- Örnek birimler: `px`, `em` (1em = 16px varsayılan tarayıcı boyutu)

**Örnek Kullanım :**
```css

/* Anahtar kelime ile */
h1 {
    font-size: large;
}

/* Piksel ile */
p {
    font-size: 18px;
}

/* em ile */
span {
    font-size: 1.5em; /* 1.5 * 16px = 24px */
}

/* Yüzde ile */
div {
    font-size: 120%; /* 16px * 1.2 = 19.2px */
}
```

>**NOT :**
>
> Responsive tasarım için `px` yerine `em` veya `%` kullanmak daha uygundur; çünkü font boyutları ebeveyn elementlere göre ölçeklenir.

---

###  Font-Weight Özelliği
- `font-weight: x;` → Bir elementin **yazı kalınlığını** belirler.
- `x` yerine değer olarak **anahtar kelimeler** veya **sayısal değerler (100–900)** kullanılabilir.
- Anahtar kelimeler: `lighter`, `normal`, `bold`, `bolder`

**Örnek Kullanım :**
```css

/* Normal kalınlık */
p {
    font-weight: normal;
}

/* Kalın yazı */
h1 {
    font-weight: bold;
}

/* Daha ince yazı */
span {
    font-weight: lighter;
}

/* Daha kalın yazı */
h2 {
    font-weight: bolder;
}

/* Sayısal değer ile */
div {
    font-weight: 600; /* Orta kalınlık */
}
```

>**NOT :**
>
> `Font-weight`, yazı tipinin desteklediği ağırlık değerlerine bağlıdır; bazı fontlarda tüm ağırlıklar bulunmayabilir.

---

### Font-Style Özelliği
- `font-style: x;` → Bir elementin **yazı stilini** belirler.
- `x` yerine `normal` veya `italic` değerleri kullanılır.
  - `normal` → Yazı **düz**, standart görünür.
  - `italic` → Yazı **eğik**, italik görünür.

**Örnek Kullanım :**
```css

/* Normal yazı stili */
p {
    font-style: normal;
}

/* İtalik yazı stili */
em {
    font-style: italic;
}

/* Başlıkta italik yazı */
h1 {
    font-style: italic;
}

/* Span üzerinde normal yazı */
span {
    font-style: normal;
}
```

> **NOT :**
>
> `Font-style` genellikle **başlıklar, vurgular ve italik metinler** için kullanılır.

---

### Font-Variant Özelliği
- `font-variant: x;` → Bir elementin **yazı karakterlerinin** küçük harf boyutunda ama büyük harfle gösterilmesini sağlar.
- `x` yerine `normal` veya `small-caps` değerleri kullanılır.
  - `normal` → Yazı standart şekilde görünür.
  - `small-caps` → Küçük harfler küçük büyük harf (small caps) stilinde gösterilir.

**Örnek Kullanım :**
```css

/* Normal yazı */
p {
    font-variant: normal;
}

/* Small caps yazı */
h1 {
    font-variant: small-caps;
}

/* Span üzerinde small caps */
span {
    font-variant: small-caps;
}

/* Başlıkta normal stil */
h2 {
    font-variant: normal;
}
```

> **NOT :**
>
> `Small-caps` özellikle başlıklar ve vurgulu metinlerde estetik ve okunabilirlik için tercih edilir.

---

### Text-Transform Özelliği
- `text-transform: x;` → Bir elementin **yazıdaki harfleri büyük veya küçük** olarak değiştirmesini sağlar.
  - `x` yerine kullanılabilecek değerler:
    1. `none` → Yazı olduğu gibi kalır.
    2. `lowercase` → Tüm harfler küçük yapılır.
    3. `uppercase` → Tüm harfler büyük yapılır.
    4. `capitalize` → Her kelimenin ilk harfi büyük yapılır.

**Örnek Kullanım :**
```css

/* Değişiklik yapılmaz */
p {
    text-transform: none;
}

/* Tüm harfler küçük */
span {
    text-transform: lowercase;
}

/* Tüm harfler büyük */
h1 {
    text-transform: uppercase;
}

/* Her kelimenin ilk harfi büyük */
h2 {
    text-transform: capitalize;
}
```

> **NOT :**
>
> `text-transform` genellikle başlıklar, menü öğeleri veya vurgulu metinler için kullanılır.

---

### Text-Decoration Özelliği
- `text-decoration: x;` → Bir elementin **metin üzerindeki çizgisel efektlerini** belirler.
  - `x` yerine kullanılabilecek değerler:
    1. `none` → Çizgi uygulanmaz.
    2. `underline` → Metnin altı çizilir.
    3. `overline` → Metnin üstü çizilir.
    4. `line-through` → Metin çizgi ile üstü çizilir (üstü çizili metin).

**Örnek Kullanım :**

```css

/* Çizgi uygulanmaz */
p {
    text-decoration: none;
}

/* Altı çizili metin */
a {
    text-decoration: underline;
}

/* Üstü çizili metin */
h1 {
    text-decoration: overline;
}

/* Üstü çizili metin (silinmiş gibi) */
span {
    text-decoration: line-through;
}
```

> **NOT :**
>
> `text-decoration` özellikle linkler, başlıklar ve vurgu yapılacak metinler için sık kullanılır.

---

### Harf, Kelime, Satır ve Paragraf Aralıkları
- letter-spacing: x; → **Harfler arasındaki boşluğu** ayarlar.
  - x genellikle em birimi ile verilir.
- word-spacing: x; → **Kelimeler arasındaki boşluğu** ayarlar.
  - x genellikle em birimi ile verilir.
- text-indent: x; → **Paragrafın ilk satırındaki girintiyi** ayarlar.
  - x em veya px birimi ile verilebilir.
- line-height: x; → **Satırlar arasındaki yüksekliği** ayarlar.
  - x em, px veya sayı (oran) şeklinde verilebilir.

**Örnek Kullanım :**

```css

/* Harfler arasını 0.1em artır */
p {
    letter-spacing: 0.1em;
}

/* Kelimeler arasını 0.5em artır */
span {
    word-spacing: 0.5em;
}

/* Paragrafın ilk satırını 2em girintili yap */
p {
    text-indent: 2em;
}

/* Satırlar arasını 1.5 em yap */
div {
    line-height: 1.5em;
}
```

> **NOT :**
>
> Bu özellikler okunabilirliği ve tasarımı artırmak için sık kullanılır, özellikle metin bloklarında ve paragraflarda önemlidir.

---

### Text-Align Özelliği
- `text-align: x;` → Bir paragraf veya blok içindeki metnin yatay hizalamasını belirler.
  - `x` yerine kullanılabilecek değerler:
    1. `left` → Metni sola hizalar.
    2. `right` → Metni sağa hizalar.
    3. `center` → Metni ortalar.
    4. `justify` → Metni iki yana yaslar, satır sonlarını eşitler.

**Örnek Kullanım :**

```css
p {
    text-align: left;
}

h1 {
    text-align: center;
}

div {
    text-align: right;
}

article {
    text-align: justify;
}
```

>**NOT :**
>
> `text-align` özellikle başlıklar, paragraflar ve blok metinler için kullanılır ve sayfa düzeninde önemli rol oynar.

---

### Background Özellikleri
- `background: x;` → Arka planın renk, resim, tekrar, konum gibi tüm ayarlarını tek satırda yapar.
- `background-color: x;` → Arka plan rengini belirler.
  - `x` renk adı, `#rrggbb` veya `rgb(rrr, ggg, bbb)` olabilir.
- `background-image: url(resim_konumu);` → Arka plana resim ekler.
- `background-repeat: x;` → Arka plan resminin tekrarını belirler.
  - `no-repeat` → Tek sefer gösterir.
  - `repeat-x` → Yatayda tekrar eder.
  - `repeat-y` → Dikeyde tekrar eder.
  - `repeat` → Hem yatay hem dikey tekrar eder.
- `background-attachment: x;` → Arka planın kayıp kaymamasını belirler.
  - `scroll` → Sayfa kaydığında arka plan da kayar.
  - `fixed` → Arka plan sabit kalır.
- `background-position: x;` → Arka plan resminin konumunu ayarlar.
  - `x y` → Resmin sol ve üst kenara olan mesafesi.
  - Örnek: `left top`, `center center`, `right bottom` vb.
- `background-size: x;` → Arka plan resminin genişliği ve yüksekliğini belirler.
  - `xpx ypx` veya `%` ile verilebilir.
 
**Örnek Kullanım :**
```css
body {
    background-color: #f0f0f0;
}

div.header {
    background-image: url('header.jpg');
    background-repeat: no-repeat;
    background-position: center top;
    background-attachment: fixed;
    background-size: cover;
}

/* Kısaltma ile tek satır */
section.hero {
    background: #333 url('hero.jpg') no-repeat center center;
}
```

- Tek satırda yazmak için:
```css
background: renk url(resim_konumu) tekrar pozisyon;
```

> **NOT :**
>
> `background` özellikleri sayfanın görselliği ve estetiği için kritik öneme sahiptir. Arka plan resimleri ve renkleri ile tasarım bütünlüğü sağlanır.

---

### Column-Count Özelliği
- `column-count: x;` → Bir container içindeki içeriği **belirtilen sayıda dikey kolona** böler.
- `x` yerine kolon sayısı (sayı) gelir.
- Genellikle **metinleri veya listeleri çok sütunlu düzenlemek** için kullanılır.

**Örnek Kullanım :**

```css
div.news {
    column-count: 3;
}

section.articles {
    column-count: 2;
}

ul.features {
    column-count: 4;
}
```

> **NOT :**
>
> `column-count` ile birlikte column-gap özelliği kullanarak sütunlar arası boşluğu da ayarlayabilirsiniz.

---

### Tarayıcı ve Ekran Uyumluluğu
- **Normalize ve Reset**
  - `normalize.css` → Normalize CSS, farklı tarayıcıların aynı HTML elementini farklı göstermesini engelleyen bir CSS dosyasıdır.
        Yani elementlerin varsayılan stillerini tamamen silmez, sadece tarayıcılar arasındaki farkları eşitler.
  - `reset.css` → Reset, tüm HTML elementlerinin varsayılan stillerini sıfırlar (resetler). Yani margin, padding gibi değerler             tamamen kaldırılır. Böylece tasarıma sıfırdan başlanır.
  - Böylece web sayfası **tüm tarayıcılarda aynı** görünür.
- **Responsive ve Adaptive Tasarım**
  - **Responsive** → Sayfa, ekran boyutuna göre esnek şekilde uyum sağlar.
    - Örnek: `width: 100%`, `flex`, `grid` kullanımı.
  - **Adaptive** → Sayfa, belirli ekran boyutları için önceden tanımlanmış tasarımlar uygular.
    - Örnek: `@media screen and (max-width: 768px) { ... }`

**Örnek Kullanım :**
```css
/* Normalize CSS - Basit Örnek */

html {
    line-height: 1.15;
}

body {
    margin: 0;
}

h1 {
    font-size: 2em;
    margin: 0.67em 0;
}

img {
    border-style: none;
}

button,
input,
select,
textarea {
    font-family: inherit;
    font-size: 100%;
    margin: 0;
}

/* Reset CSS - Basit Örnek */

/* Tüm elementlerin varsayılan boşluklarını sıfırla */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Liste işaretlerini kaldır */
ul, ol {
    list-style: none;
}

/* Linklerin varsayılan görünümünü kaldır */
a {
    text-decoration: none;
    color: inherit;
}

/* Resimleri daha esnek yap */
img {
    max-width: 100%;
    display: block;
}

/* Butonların varsayılan stilini kaldır */
button {
    border: none;
    background: none;
    cursor: pointer;
}

/* Başlıkların varsayılan boyutlarını sıfırla */
h1, h2, h3, h4, h5, h6 {
    font-size: inherit;
    font-weight: normal;
}

/* Responsive Tasarım */

.container {
    width: 80%;
    margin: auto;
}

/* Tablet */
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}

/* Telefon */
@media (max-width: 480px) {
    .container {
        width: 100%;
    }
}

@media (min-width: 600px) and (max-width: 900px) {
    .container {
        background-color: lightblue;
        width: 90%;
    }
}

/* Adaptive Tasarım */

/* Masaüstü */
.container {
    width: 1200px;
}

/* Tablet */
@media (max-width: 768px) {
    .container {
        width: 700px;
    }
}

/* Telefon */
@media (max-width: 480px) {
    .container {
        width: 350px;
    }
}

@media (min-width: 768px) and (max-width: 1024px) {
    body {
        font-size: 18px;
    }
}
```

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Seçici İşlemleri**](02-seçici-işlemleri.md)  
**➡️ Sonraki:** [**Kutu Modeli**](04-kutu-modeli.md)
