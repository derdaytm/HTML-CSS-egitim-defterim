## CSS Kodlarını Yazma Yöntemleri

### 1. Inline (Satır İçi)
  - HTML tagının içine `style` attribute’u eklenir. Küçük değişiklikler için uygundur, genellikle önerilmez.   
    Örnek Kullanım :
    ```html
    <!-- Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. -->
    
    <!DOCTYPE html>
    <html lang="tr">
    <head>
        <meta charset="UTF-8">
        <title>Inline CSS Örneği</title>
    </head>
    <body>
        <h1 style="color: red; text-align: center;">Merhaba Dünya!</h1>
        <p style="color: blue; font-size: 18px;">Bu paragraf satır içi CSS ile stillendirildi.</p>
    </body>
    </html>
    ```

### 2. Internal (Dahili)
  - `<head>` içinde `<style>` etiketi kullanılarak yazılır. Sayfanın tüm elementleri için geçerlidir.   
    Örnek Kullanım :
    ```html
    <!-- Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. -->
    
    <!DOCTYPE html>
    <html lang="tr">
    <head>
        <meta charset="UTF-8">
        <title>Internal CSS Örneği</title>
        <style>
            body {
                font-family: Arial, sans-serif;
                background-color: #f5f5f5;
            }
            h1 {
                color: green;
                text-align: center;
            }
            p {
                color: purple;
                font-size: 16px;
            }
        </style>
    </head>
    <body>
        <h1>Merhaba Dünya!</h1>
        <p>Bu paragraf dahili CSS ile stillendirildi.</p>
    </body>
    </html>
    ```

  ### External (Harici)
  - Ayrı bir CSS dosyası oluşturulur ve HTML’e `<link>` ile bağlanır. Büyük projeler için en sağlıklı yöntemdir.   
    Örnek Kullanım :   
      CSS dosyası :
      ```css
       /* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

      body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #e0f7fa;
      }
      
      h1 {
          color: orange;
          text-align: center;
      }
      
      p {
          color: navy;
          font-size: 16px;
      }
      ```
      HTML dosyası :
      ```html
      <!DOCTYPE html>
      <html lang="tr">
      <head>
          <meta charset="UTF-8">
          <title>External CSS Örneği</title>
          <link rel="stylesheet" type="text/css" href="stil.css">
      </head>
      <body>
          <h1>Merhaba Dünya!</h1>
          <p>Bu paragraf harici CSS dosyası ile stillendirildi.</p>
      </body>
      </html>
      ```

> **NOT :**
>
> Inline sadece küçük, tek seferlik değişiklikler için uygundur. Internal küçük projelerde tercih edilebilir.
> External yöntem büyük projelerde ve tekrar kullanılacak stillerde en iyi uygulamadır.

## CSS Seçicileri ve Uygulama Yöntemleri

  ### 1. HTML Tagına CSS Uygulamak
  - Direkt olarak tag ismi yazılarak uygulanabilir.   
    Örnek Kullanım :
    ```html
    <!-- Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. -->

    p {
    color: blue; /* Tüm <p> tagları mavi olur */
    }
    ```

  ### 2. ID ile CSS Uygulamak
  - ID için `#` işareti kullanılır.   
  Örnek Kullanım :
    - HTML : `<div id="header"> ... </div>`
    - CSS :
      ```css
      /* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

      #header {
          background-color: #333;
      }
      ```

  ### 3. Class ile CSS Uygulamak
  - Class için `.` işareti kullanılır ve HTML tagında `class="isim"` eklenir.   
    Örnek Kullanım :
      - HTML : `<div class="kutu">...</div>`
      - CSS :
        ```css
        /* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

        .kutu {
            border: 1px solid black;
        }
        ```

  ### Birden Fazla Selector Kullanımı
  -  Birden fazla tag veya class seçiciye `,` ile toplu stil uygulanabilir.   
    Örnek Kullanım :
      ```css
      /* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

      h1, p, .baslik, #isimler { // h1 ve p tagıyla beraber class baslik olan ve id isimler olanı da seçtik
        color: red;
      }
      ```

---

## CSS Seçicileri (Selectors)
- CSS kuralları bir elemente **birden fazla yerden uygulanabiliyorsa**, hangi kuralın geçerli olacağını belirlemek için öncelik sıralaması vardır.
- **Öncelik sıralaması** şu şekildedir:
  - **Tag içi (Inline)** → HTML elementinin içine direkt yazılan style attribute’u
  - **Head içi (Internal)** → `<head>` kısmında `<style>` etiketiyle yazılan CSS
  - **Harici (External)** → Ayrı CSS dosyasında yazılan kurallar ve `<link>` ile bağlanan dosya
- Yani **inline > internal > external** olarak geçerlidir.
- Bu sırayla CSS kuralları **çakışma olduğunda** hangisinin uygulanacağını belirler.

> **NOT :**
>
> Buradaki tüm örnekleri ezberlemenize gerek yok.   
> Önemli olan **temel mantığı anlamaktır**.    
> İlk 9-10 örneği anladıysanız, diğerlerini ihtiyaç oldukça buradan kontrol ederek kullanabilirsiniz.   

### Tag Seçme
- HTML tagını doğrudan yazarak o tagın tamamına CSS uygulanabilir.

**Örnek Kullanım:**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p{
  color:red;
}

h1{
  font-size:30px;
}

h3{
  font-size:20px;
}
```

### İç İçe Tag Seçme

- Bir HTML tagının **içinde bulunan başka bir tagı seçmek** için iki tag **boşluk bırakılarak** yazılır.
- Bu yöntem **ebeveyn → çocuk ilişkisini** belirtir.
- İlk yazılan tag **üst (parent)**, ikinci yazılan tag **içindeki (child)** elemandır.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p strong{
  color:red;
}

div p{
  font-size:18px;
}

nav a{
  text-decoration:none;
  color:black;
}
```

### ID ile Seçme

- HTML’de `id` değeri **benzersizdir** ve sayfada **bir kez kullanılması önerilir** (HTML dosyasında aynı ıd'den sadece 1 tane olmalı).
- CSS’te `id` ile seçim yapmak için **`#` işareti** kullanılır.
- `#id_adi` yazılarak ilgili elemente stil uygulanır.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

#baslik{
  color:red;
}

#menu{
  background-color:black;
  color:white;
}

#footer{
  text-align:center;
}
```

### Class ile Seçme

- HTML’de `class` birden fazla elementte kullanılabilir (HTML dosyası içinde birden fazla taga aynı class adını vererek toplu uygulanabilir).
- CSS’te `class` ile seçim yapmak için **`.` (nokta)** kullanılır.
- `.class_adi` yazılarak o class’a sahip tüm elementlere stil uygulanır.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

.kirmizi{
  color:red;
}

.buyuk{
  font-size:30px;
}

.kutu{
  border:1px solid black;
  padding:10px;
}
```

### Tag İçinde Class veya ID Seçme

- Bazen sadece **class’ı seçmek yeterli olmaz**, belirli bir **HTML tagı içindeki class veya ID** seçilmek istenir.
- Bunun için önce **tag adı**, sonra **`.class_adi`** veya **`#ID_adi`** yazılır.
- Bu yöntem sadece **belirtilen tag + belirtilen class / ID** kombinasyonunu seçer.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p.kirmizi{
  color:red;
}

h1.baslik{
  font-size:40px;
}

div.kutu{
  border:1px solid black;
  padding:10px;
}

div#menu{
  background:black;
}

nav#ustmenu{
  height:60px;
}

section#icerik{
  padding:20px;
}

```

### Toplu Seçici Kullanma

- CSS’te **birden fazla elementi aynı anda seçmek** için seçiciler **virgül (`,`) ile ayrılır**.  
- Böylece aynı stil birden fazla tag veya id/class için geçerli olur.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

h1, p, #ex {
  color: blue;
  font-family: Arial, sans-serif;
}
```

### Ebeveyn (Parent) İlişkisi Belirtme

- CSS’te **`>` işareti**, bir ebeveyn (parent) tag ile **doğrudan altındaki çocuk (child) tagı** seçmek için kullanılır.  
- Bu yöntem, sadece **doğrudan alt elemanı** hedef alır; daha derin alt elemanlara uygulanmaz.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

div > p {
  color: green;
  font-size: 16px;
}

#başlık-container > h2 {
  color: blue;
  text-decoration: underline;
}

.menu-list > ul {
  list-style-type: square;
  margin-left: 20px;
}

```

### Pseudo-element Kullanımı (:before & :after)

- CSS’te **`:before` ve `:after` pseudo-elementleri**, seçilen elementin **içeriğinin öncesine veya sonrasına ek içerik eklemek** için kullanılır.  
- Bu eklenen içerikler **gerçek HTML içine yazılmaz**, sadece CSS ile görsel olarak gösterilir.  
- Dekoratif amaçlı veya ek bilgi göstermek için tercih edilir.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

/* 1. Başlıktan önce ve sonra simge ekleme */
h2:before {
  content: "🔥 ";
}
h2:after {
  content: " ✨";
}

/* 2. Paragrafın başına ve sonuna özel karakter ekleme */
p.note:before {
  content: "❗ ";
  color: red;
}
p.note:after {
  content: " ✅";
  color: green;
}

/* 3. Listede başa ve sona işaret ekleme */
li.item:before {
  content: "• ";
  color: blue;
}
li.item:after {
  content: " ✔";
  color: green;
}
```

### Çocuk Seçiciler (:first-child, :last-child, :nth-child, :nth-last-child)

- CSS’te **çocuk seçiciler**, bir ebeveyn elementi içindeki **belirli çocuk elementleri seçmek** için kullanılır.  
- Bu sayede liste, tablo veya herhangi bir grup içindeki öğelere özel stiller uygulanabilir.

**Seçiciler ve Kullanımı:**

1. `:first-child` → Ebeveynin **ilk çocuğunu** seçer.  
2. `:last-child` → Ebeveynin **son çocuğunu** seçer.  
3. `:nth-child(n)` → Ebeveynin **n. çocuğunu** seçer. (n sayısal veya formüllü olabilir)
4. `:nth-last-child(n)` → Ebeveynin sondan **n. çocuğunu** seçer.

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

/* 1. İlk liste öğesini kırmızı yap */
ul li:first-child {
  color: red;
}

/* 2. Son liste öğesini yeşil yap */
ul li:last-child {
  color: green;
}

/* 3. İkinci liste öğesini mavi yap */
ul li:nth-child(2) {
  color: blue;
}

/* 4. Her 2'nin katı liste öğesini farklı renk yap  */ 
ul li:nth-child(2n) {
  background-color: #f0f0f0;
}

/* 5. Sondan ikinci liste öğesini mor yap */
ul li:nth-last-child(2) {
  color: purple;
}

/* 6. Sondan her 2'nin katı olan öğeye arka plan uygula */
ul li:nth-last-child(2n) {
  background-color: #e0e0e0;
}
```

### :nth-of-type / :only-of-type Seçicileri
- `:nth-of-type(n)` → Aynı türdeki elementler içinde **belirtilen sıradaki öğeyi** seçmek için kullanılır.
- `:only-of-type` → Aynı türden elementler içinde **sadece bir öğe varsa onu** seçmek için kullanılır.
- Genellikle **bir türden birden fazla element varsa, belirli sıra veya tek olanı stil vermek** için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p:nth-of-type(2) {
    color: blue;
    font-weight: bold;
}

li:nth-of-type(3) {
    background-color: #f0f0f0;
    list-style-type: square;
}

h2:only-of-type {
    text-align: center;
    font-size: 28px;
    text-transform: uppercase;
}
```

> **NOT :**
>
> `:nth-child(n)` ve `:nth-of-type(n)` → Öğelerin belirli sıralarını seçmek için kullanılır.

### Evrensel Seçici (*)

- `*` seçici, **sayfadaki tüm HTML elementlerini** seçmek için kullanılır.  
- Özellikle **genel stilleri sıfırlamak** veya tüm elemanlara ortak stil vermek için kullanışlıdır.  

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

/* Sayfadaki tüm elementlerin margin ve padding değerini sıfırlar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Sayfadaki tüm elementlerin font-family değerini değiştirir */
* {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
```

### Root Seçici (:root)

- `:root` seçici, **HTML belgesinin en üst seviyesi olan `<html>` tagını** seçer.  
- Genellikle **CSS değişkenleri (custom properties)** tanımlamak veya global stil ayarları yapmak için kullanılır.  

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --base-font-size: 16px;
}

/* Değişkenlerin kullanımı */
body {
    font-size: var(--base-font-size);
    color: var(--primary-color);
}

button {
    background-color: var(--secondary-color);
    color: #fff;
}
```

### Empty Seçici (:empty)

- `:empty` seçici, **içeriği hiç olmayan HTML elementlerini** seçmek için kullanılır.  
- İçerik derken **metin, başka HTML tagı veya boşluk karakteri bile olmamalıdır**.  
- Genellikle, boş elemanlara özel stil vermek veya uyarı göstermek için kullanılır.  

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

div:empty {
    border: 2px dashed red;
    min-height: 50px;
    background-color: #f9f9f9;
}
```

### Not Seçici (:not)

- `:not()` seçici, **belirttiğiniz CSS seçici ile eşleşmeyen elementleri** seçmek için kullanılır.  
- Bu sayede bazı elementleri **hariç tutarak stil uygulamak** mümkün olur.  
- Çok faydalı bir seçicidir, özellikle belirli class veya id’leri dışlamak için kullanılır.  

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p:not(.vurgulu) {
    color: gray;
    font-style: italic;
}
```

### İlk Satır ve İlk Harf Seçicileri

- `::first-line` → Bir elementin **ilk satırını** seçmek için kullanılır.  
- `::first-letter` → Bir elementin **ilk harfini** seçmek için kullanılır.  
- Bu seçiciler genellikle **tipografi ve stil düzenlemelerinde** kullanılır.  

**Örnek Kullanım :**

```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p::first-line {
    font-weight: bold;
    color: blue;
}

p::first-letter {
    font-size: 2em;
    color: red;
}
```

### Only-Child Seçici

- `:only-child` seçici, bir elementin **tek çocuğu olan alt elemanını** seçmek için kullanılır.
- Eğer bir elementin birden fazla çocuğu varsa, seçici **hiçbirini seçmez**.
- Genellikle “sadece bir çocuğu olan container” gibi durumlarda stil vermek için kullanılır.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

div p:only-child {
    color: blue;
    font-weight: bold;
}

section h2:only-child {
    text-align: center;
    font-size: 24px;
}

article ul:only-child {
    list-style-type: square;
    margin-left: 20px;
}
```

### Lang (Dil) Seçici
- `[lang="x"]` seçici, bir elementin **belirli bir dile ait içeriğini** seçmek için kullanılır.
- Çok dilli sayfalarda, **sadece seçilen dildeki** elementlere stil uygulamak için tercih edilir.
- Dil kodları genelde **ISO 639-1** formatında kullanılır (örn. tr, en, fr).

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p[lang="tr"] {
    color: red;
    font-weight: bold;
}

p[lang="en"] {
    color: blue;
    font-style: italic;
}

section[lang="fr"] {
    font-size: 18px;
    text-align: center;
}
```

### Valid / Invalid Seçicileri
- `:valid` → Kullanıcının **geçerli veri girdiği** form elementlerini seçmek için kullanılır.
- `:invalid` → Kullanıcının **geçersiz veri girdiği** form elementlerini seçmek için kullanılır.
- Genellikle **form doğrulama** ve kullanıcıya geri bildirim vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input:valid {
    border: 2px solid green;
    background-color: #f9fff9;
}

input:invalid {
    border: 2px solid red;
    background-color: #fff0f0;
}

textarea:valid {
    outline: 2px solid blue;
}

textarea:invalid {
    outline: 2px solid orange;
}
```

### Enabled / Disabled Seçicileri
- `:enabled` → Aktif HTML elementlerini seçmek için kullanılır.
- `:disabled` → Pasif veya devre dışı bırakılmış HTML elementlerini seçmek için kullanılır.
- **Genellikle form elemanlarında** (input, select, textarea, button) aktif veya pasif duruma göre stil vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input:enabled {
    border: 2px solid green;
    background-color: #f9fff9;
}

input:disabled {
    border: 2px solid gray;
    background-color: #f0f0f0;
}

button:enabled {
    cursor: pointer;
    opacity: 1;
}

button:disabled {
    cursor: not-allowed;
    opacity: 0.5;
}
```

### Checked Seçici
- `:checked` → İşaretli onay kutusu (`checkbox`) veya seçenek kutusu (`radio`) gibi elementleri seçmek için kullanılır.
- Genellikle kullanıcının **seçim yaptığı öğelere özel stil** vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input[type="checkbox"]:checked {
    accent-color: green;
    outline: 2px solid green;
}

input[type="radio"]:checked {
    accent-color: blue;
}

label input:checked + span {
    font-weight: bold;
    color: red;
}
```

### Required / Optional Seçicileri
- `:required` → Formda **gerekli olan elementleri** seçmek için kullanılır.
- `:optional` → Formda **opsiyonel olarak veri girilebilen elementleri** seçmek için kullanılır.
- Genellikle **form validasyonu ve stil uygulamaları** için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input:required {
    border: 2px solid red;
    background-color: #fff0f0;
}

input:optional {
    border: 2px solid gray;
    background-color: #f9f9f9;
}

textarea:required {
    outline: 2px solid blue;
}

textarea:optional {
    outline: 2px solid lightgray;
}
```

> **NOT :**
>
> `:checked`, `:disabled`, `:enabled`, `:required` → Genellikle form elemanları ile kullanılır.

### Link / Visited / Active / Hover / Focus Seçicileri
- `:link` → Ziyaret edilmemiş linkleri seçmek için kullanılır.
- `:visited` → Ziyaret edilmiş linkleri seçmek için kullanılır.
- `:active` → Tıklanan ve fare bırakılana kadar aktif olan linkleri seçmek için kullanılır.
- `:hover` → Fare imleci üzerindeyken link veya elementleri seçmek için kullanılır.
- `:focus` → Fareyle tıklanan veya klavye ile aktif olan elementleri seçmek için kullanılır.
- `:target` → Sayfadaki hedeflenen (id ile seçilmiş) öğeyi seçmek için kullanılır.
- Genellikle **link durumları ve kullanıcı etkileşimi** için tercih edilir.

> **NOT :**
>
> `:hover` ve `:focus` → Etkileşimli öğeler için kullanılır.
> `:link` ve `:visited` → Bağlantıların durumuna göre seçim yapar.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

a:link {
    color: blue;
    text-decoration: none;
}

a:visited {
    color: purple;
}

a:active {
    color: red;
}

a:hover {
    color: green;
    text-decoration: underline;
}

input:focus {
    border: 2px solid orange;
    background-color: #fff8e1;
}

#section1:target {
    border: 2px solid red;
    background-color: #fff0f0;
    padding: 10px;
}
```

### :first-of-type / :last-of-type Seçicileri
- `:first-of-type` → Aynı türdeki elementler içinde **ilk olanı** seçmek için kullanılır.
- `:last-of-type` → Aynı türdeki elementler içinde **sonuncuyu** seçmek için kullanılır.
- Genellikle **bir türden birden fazla element varsa, ilkine veya sonuncusuna özel stil** vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

p:first-of-type {
    color: red;
    font-weight: bold;
}

p:last-of-type {
    color: blue;
    font-style: italic;
}

li:first-of-type {
    list-style-type: square;
    background-color: #f0f0f0;
}

li:last-of-type {
    list-style-type: circle;
    background-color: #e0e0e0;
}

h2:first-of-type {
    font-size: 28px;
    text-transform: uppercase;
}

h2:last-of-type {
    font-size: 24px;
    font-style: italic;
}
```

### :in-range Seçici
- `:in-range` → `<input>` elementinde **belirli bir değer aralığında olanları** seçmek için kullanılır.
- Genellikle **number, range veya date** inputlarında kullanıcı tarafından girilen değer aralıklarını kontrol etmek ve stil vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input:in-range {
    border: 2px solid green;
    background-color: #f9fff9;
}

input[type="number"]:in-range {
    color: blue;
}

input[type="range"]:in-range {
    accent-color: orange;
}
```

### :out-of-range / :read-only / :read-write Seçicileri
- `:out-of-range` → `<input>` elementinde **belirtilen aralığın dışındaki** değerleri seçmek için kullanılır.
- `:read-only` → `<input>` elementinde **sadece okunabilir (readonly) olanları** seçmek için kullanılır.
- `:read-write` → `<input>` elementinde **hem okunabilir hem de yazılabilir** olanları seçmek için kullanılır.
- Genellikle **form validasyonu ve kullanıcıya geri bildirim** vermek için tercih edilir.

**Örnek Kullanım :**
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

input:out-of-range {
    border: 2px solid red;
    background-color: #fff0f0;
}

input:read-only {
    border: 2px dashed gray;
    background-color: #f5f5f5;
}

input:read-write {
    border: 2px solid green;
    background-color: #f9fff9;
}

/* Number input örneği */
input[type="number"]:out-of-range {
    color: red;
}

input[type="text"]:read-only {
    font-style: italic;
}

input[type="text"]:read-write {
    font-weight: bold;
}
```

### CSS Özellik Seçicileri
- **Özellik seçicileri**, HTML elementlerinin belirli **özelliklerine veya değerlerine** göre stil uygulamak için kullanılır.
- Kullanım şekilleri:
  - `[özellik]` → Belirli bir özelliğe sahip olan öğeleri seçer.
  - `[özellik=değer]` → Özelliği belirli bir değere sahip öğeleri seçer.
  - `[özellik^=değer]` → Özelliği belirli bir değerle başlayan öğeleri seçer.
  - `[özellik$=değer]` → Özelliği belirli bir değerle biten öğeleri seçer.
  - `[özellik*=değer]` → Özelliği içinde belirli bir metin bulunan öğeleri seçer.

**Örnek Kullanım :** 
```css
/* Burada temel yapıyı anlamamız yeterlidir. Yazılan kodlar daha sonra anlatılacaktır. */

/* 1. type özelliğine sahip inputlar */
input[type] {
    border: 2px solid gray;
    padding: 5px;
}

/* 2. type="text" olan inputlar */
input[type="text"] {
    background-color: #f9f9f9;
    color: #333;
}

/* 3. target="_blank" olan linkler */
a[target=_blank] {
    color: blue;
    text-decoration: underline;
}

/* 4. title içinde "kedi" geçen img etiketleri */
img[title*="kedi"] {
    border: 2px solid orange;
}

/* 5. class içinde "menu" metni olan divler */
div[class~="menu"] {
    background-color: #f0f0f0;
    padding: 10px;
}

/* 6. href "https" ile başlayan linkler */
a[href^="https"] {
    font-weight: bold;
}

/* 7. href ".pdf" ile biten linkler */
a[href$=".pdf"] {
    color: red;
}

/* 8. href içinde "pdf" metni geçen linkler */
a[href*="pdf"] {
    text-decoration: line-through;
}
```

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Temel Bilgiler**](01-temel-kavramlar.md)  
**➡️ Sonraki:** [**Metinlerin Biçimlendirilmesi**](03-metinlerin-biçimlendirmesi.md)
