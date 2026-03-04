## Meta Etiketleri

> Meta etiketleri **kapatılmaz** ve `<head>` içinde kullanılır. Sayfanın tarayıcıya veya arama motorlarına iletmek istediği bilgileri içerir.

### Karakter Seti
- `<meta charset="UTF-8">` → Sayfanın karakter kümesini tanımlar. Modern sayfalarda **UTF-8** önerilir.

### Sayfa Açıklaması ve Anahtar Kelimeler
- `<meta name="description" content="Web sayfasının açıklaması">` → Arama motorları ve sosyal paylaşımda sayfanın özetini gösterir.
- `<meta name="keywords" content="html, css, javascript">` → Arama motorları için anahtar kelimeler tanımlar (modern SEO’de etkisi azdır).
- `<meta name="author" content="Yazar Adı">` → Sayfanın yazarını belirtir.

### Robots ve Arama Motoru Kontrolü
- `<meta name="robots" content="index, follow">` → Sayfanın indekslenmesini ve linklerin takip edilmesini sağlar.
- `noindex, nofollow` → İndekslenmeyi ve link takibini engeller.

### Yenileme ve HTTP-EQUIV
- `<meta http-equiv="refresh" content="5">` → Sayfanın **5 saniyede bir yenilenmesini** sağlar.
- `<meta http-equiv="content-type" content="text/html; charset=UTF-8">` → Eski yöntem; sayfanın karakter kodlamasını belirtir.
- `<meta http-equiv="default-style" content="varsayılan-stil.css">` → Varsayılan CSS dosyasını belirtir.
- `<meta http-equiv="X-UA-Compatible" content="IE=edge">` → Eski Internet Explorer uyumluluğu sağlar.

### Görünüm ve Mobil Uyumluluk
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` → Mobil cihazlarda **ekran boyutuna göre ölçekleme** sağlar.
  - `width=device-width` → Ekran genişliğine göre ayarlar.  
  - `initial-scale=1.0` → Başlangıçta 1:1 zoom uygular.
  - Örnek: `<meta name="viewport" content="width=600, initial-scale=1.0">` → Sabit genişlik, mobilde bozulabilir.

### Sosyal Medya ve Paylaşım
- `<meta property="og:title" content="Sayfa Başlığı">` → Open Graph, sosyal medya paylaşımı için başlık.
- `<meta property="og:description" content="Sayfa açıklaması">` → Paylaşıldığında açıklama.
- `<meta property="og:image" content="resim.png">` → Paylaşım görseli.
- `<meta name="twitter:card" content="summary_large_image">` → Twitter paylaşımı için kart türü.

### Güvenlik ve Yönlendirme
- `<meta http-equiv="Content-Security-Policy" content="default-src 'self'">` → Sayfada izin verilen kaynakları sınırlar.
- `<meta http-equiv="refresh" content="0; url=https://yeni-sayfa.com">` → Belirli süre sonra yönlendirme.

> **NOT**  
> Meta etiketleri tek başına okunarak anlaşılması zor olabilir.  
> En iyi öğrenme yöntemi **örnek bir HTML sayfası** içine ekleyerek, tarayıcıda nasıl çalıştığını görmek ve test etmektir.

---

### Kapsamlı HTML Örneği

```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Kapsamlı Örnek Sayfa</title>
  <style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 2em; line-height: 1.5; }
    fieldset { margin-bottom: 1.5em; padding: 1em; }
    table { border-collapse: collapse; width: 100%; margin-bottom: 1em; }
    th, td { border: 1px solid #333; padding: 0.5em; text-align: left; }
    th { background-color: #eee; }
  </style>
</head>
<body>

  <header>
    <h1>Web Geliştirme Kapsamlı Örnek</h1>
    <nav>
      <a href="#form">Form</a> | <a href="#tablo">Tablo</a> | <a href="#multimedia">Medya</a>
    </nav>
  </header>

  <main>

    <!-- FORM -->
    <section id="form">
      <h2>Form Örneği</h2>
      <form name="kayitFormu" action="mail.php" method="post" enctype="multipart/form-data" autocomplete="on">

        <!-- KULLANICI BİLGİLERİ -->
        <fieldset>
          <legend>Kullanıcı Bilgileri</legend>
          <label for="fullname">Ad Soyad:</label><br>
          <input type="text" id="fullname" name="fullname" placeholder="Adınızı giriniz" required autofocus><br><br>

          <label for="email">E-posta:</label><br>
          <input type="email" id="email" name="email" placeholder="ornek@mail.com" required><br><br>

          <label for="password">Şifre:</label><br>
          <input type="password" id="password" name="password" minlength="6" required><br><br>

          <label for="phone">Telefon:</label><br>
          <input type="tel" id="phone" name="phone" placeholder="05XXXXXXXXX"
            pattern="^05[0-9]{9}$" title="05 ile başlayan 11 haneli numara giriniz"><br><br>

          <label for="website">Web Sitesi:</label><br>
          <input type="url" id="website" name="website" placeholder="https://example.com"><br><br>
        </fieldset>

        <!-- CINSIYET VE ILGI -->
        <fieldset>
          <legend>Cinsiyet ve İlgi Alanları</legend>
          <input type="radio" name="gender" value="erkek" checked> Erkek<br>
          <input type="radio" name="gender" value="kadin"> Kadın<br><br>

          <input type="checkbox" name="interest_html" value="HTML"> HTML<br>
          <input type="checkbox" name="interest_css" value="CSS"> CSS<br>
          <input type="checkbox" name="interest_js" value="JS"> JavaScript<br>
        </fieldset>

        <!-- RANGE + OUTPUT -->
        <fieldset>
          <legend>Seviye Bilgisi</legend>
          <label for="level">Seviye:</label>
          <input type="range" id="level" name="level" min="0" max="100" value="50" oninput="this.form.result.value=this.value">
          <output name="result">50</output>
        </fieldset>

        <!-- DOSYA -->
        <label>Dosya Yükle:</label><br>
        <input type="file" name="file" accept=".pdf,image/*"><br><br>

        <!-- COLOR -->
        <fieldset>
          <legend>Favori Renk</legend>
          <label for="favColor">Renk Seç:</label><br>
          <input type="color" id="favColor" name="favColor" value="#ff0000" oninput="this.form.colorResult.value=this.value">
          <output name="colorResult">#ff0000</output>
        </fieldset>

        <!-- TEXTAREA -->
        <label for="message">Mesaj:</label><br>
        <textarea id="message" name="message" rows="4" cols="40" maxlength="200" placeholder="Mesajınızı yazın" required></textarea><br><br>

        <!-- SELECT -->
        <label>Şehir:</label><br>
        <select name="city">
          <option value="">Seçiniz</option>
          <option value="istanbul">İstanbul</option>
          <option value="ankara" selected>Ankara</option>
          <option value="izmir">İzmir</option>
        </select><br><br>

        <!-- BUTTON -->
        <input type="submit" value="Gönder">
        <input type="reset" value="Temizle">
      </form>
    </section>

    <!-- TABLO -->
    <section id="tablo">
      <h2>Tablo Örneği</h2>
      <table>
        <thead>
          <tr>
            <th id="name">Ad</th>
            <th id="age">Yaş</th>
            <th id="city">Şehir</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td headers="name">Ahmet</td>
            <td headers="age">25</td>
            <td headers="city">İstanbul</td>
          </tr>
          <tr>
            <td headers="name">Ayşe</td>
            <td headers="age">30</td>
            <td headers="city">Ankara</td>
          </tr>
        </tbody>
      </table>
    </section>

    <!-- MULTIMEDIA -->
    <section id="multimedia">
      <h2>Resim ve Video Örnekleri</h2>

      <!-- IMG + LAZY LOADING + SRCSET -->
      <img src="small.png" 
           srcset="small.png 600w, medium.png 900w, big.png 1200w"
           sizes="(max-width: 600px) 100vw, (max-width: 900px) 50vw, 33vw"
           alt="Örnek Resim"
           loading="lazy"
           decoding="async"
      ><br><br>

      <!-- PICTURE ÖRNEĞİ -->
      <picture>
        <source media="(max-width: 600px)" srcset="small.png">
        <source media="(max-width: 900px)" srcset="medium.png">
        <img src="big.png" alt="Responsive Resim">
      </picture><br><br>

      <!-- VIDEO -->
      <video width="320" height="240" controls>
        <source src="video.mp4" type="video/mp4">
        Tarayıcınız video etiketini desteklemiyor.
      </video><br><br>

      <!-- AUDIO -->
      <audio controls>
        <source src="audio.mp3" type="audio/mpeg">
        Tarayıcınız audio etiketini desteklemiyor.
      </audio>

    </section>

  </main>

  <footer>
    <p>© 2026 Örnek Sayfa</p>
  </footer>

</body>
</html>
```

---

### 📚 Konu Akışı

**⬅️ Önceki:** [**Sayfa Yapısı**](08-sayfa-yapisi.md)  
