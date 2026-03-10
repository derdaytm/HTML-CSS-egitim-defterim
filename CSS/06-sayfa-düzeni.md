## Sayfa Düzeni ve Kutular

Web sayfaları genellikle **kutular (container)** üzerine kuruludur.  
Sayfa düzeni oluştururken **ana kutuların özellikleri** ile sayfanın genişliği, yüksekliği ve konumu belirlenir.

### Temel Özellikler

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `margin: auto;` | Sayfayı veya kutuyu **yatayda ortalar**. | `margin: 0 auto;` |
| `max-width: xpx;` | Kutunun veya sayfanın **maksimum genişliği**. Geniş ekranlarda sınırlama sağlar. | `max-width: 1200px;` |
| `min-height: xpx;` | Kutunun veya sayfanın **minimum yüksekliği**. Kısa içeriklerde bile belirlenen yükseklik korunur. | `min-height: 600px;` |

### Açıklama

- **Margin: auto** → Blok öğeleri yatayda ortalamak için kullanılır.  
- **Max-width** → Sayfanın çok geniş ekranlarda aşırı yayılmasını önler.  
- **Min-height** → İçerik az olsa bile sayfa yüksekliğini korur.  

> Özet: Sayfa tasarımında ana kutuların genişlik ve yüksekliği ile konumlandırma, **margin, max-width ve min-height** özellikleriyle kontrol edilir.

---

## Temel Örnekler

1. Örnek

HTML Dosyası :
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Temel Sayfa 1</title>
  <link rel="stylesheet" type="text/css" href="deneme.css">
</head>
<body>

  <header>Header</header>
  <nav>Menü</nav>
  <section>İçerik Alanı</section>
  <aside>Yan Menü / Bilgi</aside>
  <footer>Footer</footer>

</body>
</html>
```

CSS Dosyası :
```css
header, nav, section, aside, footer {
  border: 2px dashed #333; /* Bölümlerin sınırlarını çizgiyle gösterir */
  padding: 20px;
  margin: 10px 0;
}
```

***Tarayıcı Görüntüsü:**

<img width="2557" height="1362" alt="image" src="https://github.com/user-attachments/assets/4ff5a47c-b501-4c22-b344-66b652a77ad8" />

<hr>

2. Örnek

HTML Dosyası :
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Temel Sayfa 2</title>
  <link rel="stylesheet" type="text/css" href="deneme.css">
</head>
<body>

  <header>Header</header>
  <nav>Menü</nav>
  <div class="container">
    <section>Sol Sütun İçerik</section>
    <aside>Sağ Sütun Yan Menü</aside>
  </div>
  <footer>Footer</footer>

</body>
</html>
```

CSS Dosyası :
```css
header, nav, section, aside, footer {
  padding: 20px;
  margin: 10px 0;
}

header, nav, footer {
  border: 2px dashed #333; /* Üst ve alt bölümler için */
}

.container {
  display: flex; /* İki sütunu yan yana dizmek için */
  gap: 10px;     /* Sütunlar arası boşluk */
}

section, aside {
  border: 2px dashed #0077cc; /* Bölümlerin anlaşılması için çizgi */
  padding: 20px;
  flex: 1; /* İki sütunu eşit genişlik yapar */
}
```

***Tarayıcı Görüntüsü:**
<img width="2558" height="1364" alt="image" src="https://github.com/user-attachments/assets/e82a95a0-3124-4e98-a167-e6f694bef6e2" />

<hr>

3. Örnek

HTML Dosyası :
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Temel Sayfa 3</title>
  <link rel="stylesheet" type="text/css" href="deneme.css">
</head>
<body>

  <header>Header</header>
  <nav>Menü</nav>
  <div class="container">
    <section>İçerik Alanı</section>
    <aside>Yan Menü</aside>
  </div>
  <footer>Footer</footer>
  <div class="extra">Ekstra Bilgi Alanı</div>

</body>
</html>
```

CSS Dosyası :
```css
header, nav, section, aside, footer, .extra {
  border: 2px dotted #cc5500; /* Bölümlerin sınırlarını çizgiyle gösterir */
  padding: 15px;
  margin: 5px 0;
}

.container {
  display: flex;
  gap: 10px;
}

section, aside {
  flex: 1;
}
```

***Tarayıcı Görüntüsü:**
<img width="2556" height="1359" alt="image" src="https://github.com/user-attachments/assets/bcba54c6-6859-4635-a101-c505900ed1fb" />

<hr>

4. Örnek

HTML Dosyası :
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Karmaşık Sayfa Örneği</title>
  <link rel="stylesheet" type="text/css" href="deneme.css">
</head>
<body>

  <header>Header</header>

  <nav>
    <ul>
      <li>Ana Sayfa</li>
      <li>Hakkımızda</li>
      <li>Hizmetler</li>
      <li>İletişim</li>
    </ul>
  </nav>

  <div class="container">
    <section>
      <h2>İçerik Alanı</h2>
      <p>Burada makaleler, yazılar, görseller veya ana içerik bulunur.</p>
    </section>
    <aside>
      <h3>Yan Menü</h3>
      <p>Ek bilgiler, linkler veya reklamlar burada yer alabilir.</p>
    </aside>
  </div>

  <footer>Footer - Tüm Hakları Saklıdır</footer>

</body>
</html>
```

CSS Dosyası :
```css
/* Ortak stiller ve kutu modeli */
* {
  box-sizing: border-box; /* Padding ve border width içine dahil */
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
}

/* Header */
header {
  background-color: #4CAF50;
  color: white;
  text-align: center;
  padding: 20px;
  border: 2px dashed black; /* Bölümlerin anlaşılması için çizgi */
}

/* Navigasyon */
nav {
  background-color: #333;
  color: white;
  padding: 15px;
  border: 2px dashed black;
}
nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  gap: 10px;
}
nav ul li {
  padding: 5px 10px;
  background-color: #555;
  color: white;
  border-radius: 5px;
}

/* Ana içerik ve aside */
.container {
  display: flex;
  flex-wrap: wrap; /* Dar ekranlarda alt satıra kaydırır */
  gap: 10px;
  margin: 10px;
}

section {
  flex: 3;
  padding: 20px;
  border: 2px dashed #0077cc;
  background-color: #e0f7fa;
  min-height: 200px;
}

aside {
  flex: 1;
  padding: 20px;
  border: 2px dashed #ff5722;
  background-color: #fff3e0;
  min-height: 200px;
}

/* Footer */
footer {
  background-color: #607d8b;
  color: white;
  text-align: center;
  padding: 20px;
  border: 2px dashed black;
}
```

***Tarayıcı Görüntüsü:**
<img width="2552" height="1359" alt="image" src="https://github.com/user-attachments/assets/f2a27a98-04fb-4eaf-a1b9-1f1aa49153a5" />

---

## Tam Hazır Sayfa Örneği

HTML Dosyası :
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Örnek Tam Sayfa</title>
  <link rel="stylesheet" type="text/css" href="deneme.css">
</head>
<body>

  <header>
    <h1>Örnek Web Sayfası</h1>
  </header>

  <nav>
    <ul>
      <li>Ana Sayfa</li>
      <li>Hakkımızda</li>
      <li>Hizmetler</li>
      <li>Blog</li>
      <li>İletişim</li>
    </ul>
  </nav>

  <div class="hero">
    <h2>Hero Bölümü</h2>
    <p>Bu alan öne çıkan içerik için kullanılır. Banner veya slogan yerleştirilebilir.</p>
  </div>

  <div class="container">
    <main>
      <h2>İçerik Alanı</h2>
      <p>Burada makaleler, yazılar veya görseller bulunabilir. Ana içerik bu alanda yer alır.</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla facilisi.</p>
    </main>
    <aside>
      <h3>Yan Menü / Bilgiler</h3>
      <ul>
        <li>Link 1</li>
        <li>Link 2</li>
        <li>Link 3</li>
        <li>Link 4</li>
      </ul>
    </aside>
  </div>

  <footer>
    <div class="footer-columns">
      <div class="footer-column">
        <h4>Hakkımızda</h4>
        <p>Kısa bilgi veya açıklama.</p>
      </div>
      <div class="footer-column">
        <h4>Hizmetler</h4>
        <ul>
          <li>Hizmet 1</li>
          <li>Hizmet 2</li>
          <li>Hizmet 3</li>
        </ul>
      </div>
      <div class="footer-column">
        <h4>İletişim</h4>
        <p>Email: info@example.com</p>
      </div>
      <div class="footer-column">
        <h4>Sosyal Medya</h4>
        <ul>
          <li>Facebook</li>
          <li>Twitter</li>
          <li>Instagram</li>
        </ul>
      </div>
    </div>
  </footer>

</body>
</html>
```

CSS Dosyası :
```css
/* Kutu modeli ve temel reset */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  background-color: #f5f5f5;
}

/* Header */
header {
  background-color: #4CAF50;
  color: white;
  text-align: center;
  padding: 20px;
  border: 2px dashed black; /* Bölümlerin anlaşılması için çizgi */
}

/* Logo ve başlık */
header h1 {
  font-size: 2rem;
}

/* Nav */
nav {
  background-color: #333;
  border: 2px dashed black;
}
nav ul {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 15px;
}
nav ul li {
  padding: 10px 15px;
  background-color: #555;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
nav ul li:hover {
  background-color: #777;
}

/* Hero bölümü */
.hero {
  background-color: #e0f7fa;
  border: 2px dashed #0077cc;
  text-align: center;
  padding: 50px 20px;
  margin: 10px;
}

/* Ana içerik ve sidebar */
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin: 10px;
}
main {
  flex: 3;
  background-color: #fff3e0;
  border: 2px dashed #ff5722;
  padding: 20px;
  min-height: 250px;
}
aside {
  flex: 1;
  background-color: #fce4ec;
  border: 2px dashed #e91e63;
  padding: 20px;
  min-height: 250px;
}

/* Footer */
footer {
  background-color: #607d8b;
  color: white;
  border: 2px dashed black;
  padding: 20px;
}
.footer-columns {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: space-between;
}
.footer-column {
  flex: 1;
  min-width: 150px;
}
```

**Tarayıcı Çıktısı**
<img width="2553" height="1362" alt="image" src="https://github.com/user-attachments/assets/40e32694-92f6-4ce3-a095-47ae9ee0f7af" />

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Tablo ve Menü Tasarımı**](05-tablo-ve-menü-tasarımı.md)
