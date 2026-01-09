## `<form>`

- `<form>` → Form oluşturmak için kullanılan ana etikettir.
- Form etiketi içine yazılan tüm alanlar gönderime dahil edilir.
- Form içine direk yazı yazılabilir.

> **NOT**  
> Bu bölüm tek bir kapsamlı örnek üzerinden anlatılmıştır.  
> Form konusu oldukça geniştir ve yalnızca okuyarak değil, **örnekler üzerinde birebir inceleme ve deneme yapılarak** anlaşılır.  
> Bu nedenle form yapıları, **örnekle birlikte incelendiğinde** ve farklı senaryolar uygulanarak çalışıldığında kalıcı şekilde öğrenilir.

---

### Temel Özellikler

- `name="x"` → Forma isim verir.
- `action="x"` → Form verilerinin gönderileceği sayfayı belirtir.
  - `mail.php` → Veriler sunucu tarafına gönderilir ve backend tarafında işlenir.
  - `mailto:mail@example.com` → Veriler kullanıcının e-posta uygulaması ile mail olarak gönderilir.
    - Bu kullanımda `enctype="text/plain"` eklenmelidir.
- `method="x"` → Verilerin gönderilme yöntemini belirler.
  - `get` → Veriler URL üzerinden gider (gizli değildir, (512kb) sınırlıdır).
  - `post` → Veriler gizli gider, boyut sınırı yoktur. (varsayılan)

> Varsayılan method **POST** kabul edilir.

---

### enctype

- Form verilerinin hangi formatta gönderileceğini belirler.
- `application/x-www-form-urlencoded` → Varsayılan gönderim türü. Sadece metin içeren formlar için uygundur.
- `multipart/form-data` → Dosya yükleme yapılan formlar için ZORUNLUDUR. `type="file"` kullanılan her formda mutlaka eklenmelidir.
- `text/plain` → Mailto ile kullanımda tercih edilir. Nadiren tercih edilir.

---

### `<fieldset>` ve `<legend>`

- `<fieldset>` → Form elemanlarını gruplamak için kullanılır.
- `<legend>` → Grubun başlığını belirtir.

> Sadece görsel değil, **anlamsal (semantic)** gruplama yapar.
> Ekran okuyucular bu yapıyı algılar.

---

### `<label>`

- Form elemanlarını tanımlar.
- Kullanıcı deneyimi ve erişilebilirlik için ÖNEMLİDİR.

---

### `for="x"`

- `for="x"` → Hangi input’a ait olduğunu belirtir.
  - `for` değeri, input’un `id` değeriyle aynı olmalıdır.

---

### `<input>`

- Metin kutusu ve form elemanları oluşturur.
- Kapatılmaz (`/>` yoktur).
- `name` attribute'u ZORUNLUDUR.

#### `<input>` Türleri

-`type = "x"` → Form elemanının tipini belirler.
- `text` → Tek satırlı metin girişi
- `password` → Girilen karakterleri gizler
- `email` → E-posta adresi girişi (format kontrolü yapar)
- `url` → Web adresi girişi (URL formatını kontrol eder)
- `tel` → Telefon numarası girişi
- `number` → Sayısal değer girişi (`max` ve `min` ile sınırlama yapılabilir)
- `range` → Kaydırmalı çubuk ile sayı seçimi (`max` ve `min` ile sınırlama yapılabilir) (`output` kullanarak sağ tarafında çıktı gösterilebilir)
- `date` → Tarih seçimi (`max="1979-12-31"` gibi `max` ve `min` değeri girilebilir)
- `time` → Saat seçimi
- `datetime-local` → Tarih ve saat birlikte
- `month` → Ay ve yıl seçimi
- `week` → Yıl içindeki hafta seçimi
- `color` → Renk seçici açar (`Output` kullanarak sağ tarafında çıktı ile renk kodu gösterilebilir)

---

### `checkbox` ve `radio`

`<input type="checkbox-radio">` özelliğiyle kullanılır.

- `checkbox` → Onay kutusu oluşturur.
  - Birden **fazla seçenek aynı anda** seçilebilir.
  - `<input>` etiketi kapatıldıktan sonra açıklama metni yazılır.
  - Yeni satıra geçmek için `<br>` kullanılır.
  - **`name` mutlaka verilmelidir**, çünkü gönderilen veri bu isimle iletilir.

- `radio` → Tek seçim yapılmasını sağlar.
  - Bir grupta **sadece bir seçenek** seçilebilir.
  - Aynı gruba ait tüm `radio` inputlarının **`name` değeri aynı olmalıdır**.
  - Farklı `name` verilirse, her biri ayrı ayrı seçilebilir.

---

### accept (Dosya Türü Kısıtlama)

`<input type="file">` özelliğiyle kullanılır.
`accept` özelliği, **yüklenebilecek dosya türlerini sınırlandırmak** için kullanılır.

#### Dosya Uzantısına Göre
- `accept=".pdf"` → Sadece PDF
- `accept=".jpg,.jpeg,.png"` → Sadece resim dosyaları
- `accept=".doc,.docx"` → Word dosyaları
- `accept=".xls,.xlsx"` → Excel dosyaları
- `accept=".zip,.rar"` → Sıkıştırılmış dosyalar
- `accept=".mp3"` → Ses dosyaları
- `accept=".mp4"` → Video dosyaları

#### MIME Type’a Göre
- `accept="image/*"` → Tüm resimler
- `accept="video/*"` → Tüm videolar
- `accept="audio/*"` → Tüm ses dosyaları
- `accept="application/pdf"` → PDF dosyaları
- `accept="application/msword"` → Word (eski format)

#### Birlikte Kullanım
- `accept=".pdf,image/*"` → PDF **veya** resim dosyaları

> **Notlar**
> - `accept` sadece **kullanıcıya rehberlik eder**, güvenlik değildir.
> - Gerçek kontrol **sunucu tarafında** yapılmalıdır.
> - Dosya yükleme için formda `enctype="multipart/form-data"` zorunludur.
> - `get` methodu için kullanışlı değildir.

---

#### Buton türleri

`<input type="button">` özelliğiyle birlikte kullanılır.

- submit → Formu gönderir.
- reset → Formu temizler.
- image → Resim ile gönderme (*`src` ile dosya konumu belirtilmeli*)

---

### type="search" (Arama Alanı)

- `type="search"` → Arama motoru mantığında çalışan input alanıdır.
- Kullanıcı arama yapıyormuş hissi verir.
- Tarayıcıya göre temizleme (❌) butonu gösterebilir.
- `datalist` ile birlikte kullanıldığında **öneri listesi** sunar.

### list + datalist Kullanımı

- `list` → Input’un hangi `datalist` ile eşleşeceğini belirtir.
- `datalist` → Öneri listesini tutan etikettir.
- `option` → Listede gösterilecek seçenekleri tanımlar.
- Kullanıcı ister listedekini seçer, ister kendi değerini yazar.

---

### `<input>` Attribute'ları

- name → Metin kutusuna isim vermeyi sağlar.
- autofocus → Sayfa açılınca imleç otomatik gelir.
- autocomplete="on/off" → Önceki verileri önerir. (*Varsayılan olarak açık gelir*)
- placeholder="x" → Gölge açıklama metni. Valueden farkı gölge olarak gözükür.
- value="x" → Varsayılan değer.
- size="x" → Karakter genişliği.
- minlength / maxlength → Karakter sınırı.
- min / max → Sayısal sınırlar.
- required → Boş bırakılamaz.
- disabled → Pasif hale getirir.
- readonly → Sadece okunabilir.
- checked → Otomatik seçili.
- pattern → Giriş kuralı tanımlar. (*regex kuralları uygulanacaktır*) (*Sık kullanılan regexlere sayfa sonunda yer verilmiştir*)
- title → Açıklama gösterir. (*imleç üstüne geldiğinde*)
- Style =”width : xpx” → Metin kutusunun uzunluğunu belirlemeyi sağlar.

---

### <textarea>

- Çok satırlı metin girişi sağlar.

#### Özellikler

- **`name`** → Form gönderildiğinde textarea verisinin gönderileceği isimdir.
- **`rows`** → Textarea’nın dikeyde kaç satır yüksekliğinde olacağını belirler.
- **`cols`** → Textarea’nın yatayda yaklaşık kaç karakter genişliğinde olacağını belirler.
- **`maxlength`** → Girilebilecek maksimum karakter sayısını sınırlar.
- **`placeholder`** → Alan boşken görünen açıklama metnidir. Valueden farkı gölge olarak gözükür.
- **`value="x"`** → Varsayılan değer.
- **`autofocus`** → Sayfa açıldığında imlecin otomatik olarak bu alana gelmesini sağlar.
- **`autocomplete`** → Tarayıcının önceki girişleri önerip önermeyeceğini belirler.
- **`required`** → Alanın boş bırakılmasını engeller.
- **`disabled`** → Alanı pasif hale getirir ve form gönderimine dahil etmez.

---

### `<select>`

- Açılır liste oluşturur.
- `value` = Değerin bize döndürülmesini sağlar ve kullanımı **zorunludur**. Yani volvo yazdıysak valuede volvo olmalıdır.

#### Özellikler

- multiple → Çoklu seçim
- size="x" → Görünen seçenek sayısı

### `<option>`

- Seçenekleri belirtir.
- `selected` → Varsayılan seçili

### `<optgroup>`

- Seçenekleri gruplar.
- `label="x"` → Grup adı

---

### Hidden Input

- Kullanıcıya görünmez.
- Arka planda veri göndermek için kullanılır.
- `<input type="hidden" name="tarih" value="30 Temmuz">`

---

### <output>

- Hesaplanan veya üretilen sonucu göstermek için kullanılır.
- Genellikle number, range gibi inputlarla birlikte kullanılır.

---

### `<meter>`

- **Bilinen bir değerin ölçümünü** göstermek için kullanılır.
- Değerin **iyi / kötü / orta** gibi bir anlamı vardır.
- `min`, `max`, `value` ile çalışır.
- Genellikle **puan, seviye, doluluk, başarı oranı** gibi durumlar için uygundur.
- Yükleme süreci için **kullanılmaz**.

### `<progress>`

- **Devam eden bir işlemin ilerlemesini** göstermek için kullanılır.
- İşlemin **ne zaman biteceği belirsiz veya süreç halindedir**.
- `value` ve `max` ile ilerleme yüzdesi gösterilebilir.
- Dosya yükleme, işlem ilerlemesi gibi durumlar için uygundur.
- Anlamsal olarak **durum bildirir**, ölçüm yapmaz.

---

### Örnek Kullanımlar
```html
<form 
  name="kayitFormu"
  action="mail.php"
  method="post"
  enctype="multipart/form-data"
  autocomplete="on"
>

  <!-- FORM GRUPLAMA -->
  <fieldset>
    <legend>Kullanıcı Bilgileri</legend>

    <!-- LABEL + TEXT -->
    <label for="fullname">Ad Soyad:</label><br>
    <input 
      type="text"
      id="fullname"
      name="fullname"
      placeholder="Adınızı giriniz"
      required
      autofocus
    ><br><br>

    <!-- EMAIL -->
    <label for="email">E-posta:</label><br>
    <input 
      type="email"
      id="email"
      name="email"
      placeholder="ornek@mail.com"
      required
    ><br><br>

    <!-- PASSWORD -->
    <label for="password">Şifre:</label><br>
    <input 
      type="password"
      id="password"
      name="password"
      minlength="6"
      required
    ><br><br>

    <!-- TEL + PATTERN -->
    <label for="phone">Telefon:</label><br>
    <input 
      type="tel"
      id="phone"
      name="phone"
      placeholder="05XXXXXXXXX"
      pattern="^05[0-9]{9}$"
      title="05 ile başlayan 11 haneli numara giriniz"
    ><br><br>

    <!-- URL -->
    <label for="website">Web Sitesi:</label><br>
    <input 
      type="url"
      id="website"
      name="website"
      placeholder="https://example.com"
    ><br><br>

  </fieldset>

  <!-- RADIO -->
  <fieldset>
    <legend>Cinsiyet</legend>

    <input type="radio" name="gender" value="erkek" checked> Erkek<br>
    <input type="radio" name="gender" value="kadin"> Kadın<br>
  </fieldset><br>

  <!-- CHECKBOX -->
  <fieldset>
    <legend>İlgi Alanları</legend>

    <input type="checkbox" name="interest_html" value="HTML"> HTML<br>
    <input type="checkbox" name="interest_css" value="CSS"> CSS<br>
    <input type="checkbox" name="interest_js" value="JS"> JavaScript<br>
  </fieldset><br>

  <!-- NUMBER + RANGE + OUTPUT -->
  <fieldset>
    <legend>Seviye Bilgisi</legend>

    <label for="level">Seviye:</label><br>
    <input 
      type="range"
      id="level"
      name="level"
      min="0"
      max="100"
      value="50"
      oninput="this.form.result.value = this.value"
    >
    <output name="result">50</output>
  </fieldset><br>

  <!-- DATE / TIME -->
  <label>Doğum Tarihi:</label><br>
  <input type="date" name="birthdate"><br><br>

  <label>Uygun Saat:</label><br>
  <input type="time" name="time"><br><br>

 <!-- COLOR + OUTPUT -->
<fieldset>
  <legend>Favori Renk</legend>

  <label for="favColor">Renk Seç:</label><br>

  <input
    type="color"
    id="favColor"
    name="favColor"
    value="#ff0000"
    oninput="this.form.colorResult.value = this.value"
  >

  <!-- Seçilen rengin HEX kodunu gösterir -->
  <output name="colorResult">#ff0000</output>

</fieldset>

  <!-- FILE -->
  <label>Dosya Yükle:</label><br>
  <input 
    type="file"
    name="file"
    accept=".pdf,image/*"
  ><br><br>

  <!-- SEARCH + DATALIST -->
  <label for="search">Arama:</label><br>
  <input 
    type="search"
    id="search"
    name="search"
    list="techList"
    placeholder="Bir teknoloji yazın"
  >

  <datalist id="techList">
    <option value="HTML">
    <option value="CSS">
    <option value="JavaScript">
    <option value="Python">
  </datalist><br><br>

  <!-- TEXTAREA -->
  <label for="message">Mesaj:</label><br>
  <textarea
    id="message"
    name="message"
    rows="4"
    cols="40"
    maxlength="200"
    placeholder="Mesajınızı yazın"
    required
  ></textarea><br><br>

  <!-- SELECT -->
  <label>Şehir:</label><br>
  <select name="city" size="1">
    <option value="">Seçiniz</option>
    <option value="istanbul">İstanbul</option>
    <option value="ankara" selected>Ankara</option>
    <option value="izmir">İzmir</option>
  </select><br><br>

  <!-- HIDDEN -->
  <input type="hidden" name="tarih" value="30 Temmuz">

  <!-- BUTTONLAR -->
  <input type="submit" value="Gönder">
  <input type="reset" value="Temizle">

</form>
```

**Tarayıcı Çıktısı:**

<img width="760" height="568" alt="image" src="https://github.com/user-attachments/assets/e55369f2-6a6e-4c5f-8920-cebda93da016" />
<img width="759" height="547" alt="image" src="https://github.com/user-attachments/assets/96e67eed-8f3a-4d9a-a9ab-118094a2a516" />
<img width="758" height="86" alt="image" src="https://github.com/user-attachments/assets/513367f6-c24b-401c-8c28-22ada041a1ac" />

---

#### Sık Kullanılan Regex'ler

- **Sadece harf (Ad / Soyad)**
  - Regex: `^[A-Za-zÇĞİÖŞÜçğıöşü ]+$`
  - Açıklama: Harf ve boşluk kabul eder, rakam ve özel karakterleri engeller.

- **Sadece rakam**
  - Regex: `^[0-9]+$`
  - Açıklama: Yalnızca sayısal girişe izin verir.

- **Telefon numarası (Türkiye – 05 ile başlar)**
  - Regex: `^05[0-9]{9}$`
  - Açıklama: 05 ile başlar, toplam 11 hanelidir.

- **Email (genel kullanım)**
  - Regex: `^[^@\s]+@[^@\s]+\.[^@\s]+$`
  - Açıklama: @ ve alan adı uzantısını kontrol eder, boşluk kabul etmez.

- **Güçlü şifre**
  - Regex: `^(?=.*[A-Z])(?=.*[a-z])(?=.*[0-9]).{8,}$`
  - Açıklama: En az 8 karakter, 1 büyük harf, 1 küçük harf ve 1 rakam içerir.

- **Kullanıcı adı**
  - Regex: `^[a-zA-Z0-9_]{4,16}$`
  - Açıklama: Harf, rakam ve `_` içerir; 4–16 karakter arasıdır.

- **TC Kimlik Numarası (format kontrol)**
  - Regex: `^[1-9][0-9]{10}$`
  - Açıklama: 11 hanelidir ve 0 ile başlamaz (matematiksel doğrulama yapmaz).

- **URL (web adresi)**
  - Regex: `https?:\/\/(www\.)?[a-zA-Z0-9\-]+\.[a-zA-Z]{2,}`
  - Açıklama: http/https, alan adı ve uzantıyı kontrol eder.

- **Posta kodu (Türkiye)**
  - Regex: `^[0-9]{5}$`
  - Açıklama: 5 haneli sayısal giriş.

- **Sadece büyük harf**
  - Regex: `^[A-Z]+$`
  - Açıklama: Küçük harf kabul etmez.

- **Sadece küçük harf**
  - Regex: `^[a-z]+$`
  - Açıklama: Büyük harf kabul etmez.

- **Harf + rakam**
  - Regex: `^[A-Za-z0-9]+$`
  - Açıklama: Boşluk ve özel karakter içermez.

- **Ondalıklı sayı**
  - Regex: `^[0-9]+(\.[0-9]+)?$`
  - Açıklama: Tam sayı veya ondalıklı sayı kabul eder.
