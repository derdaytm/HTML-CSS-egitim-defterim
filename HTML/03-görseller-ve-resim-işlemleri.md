## Görseller ve Resim İşlemleri

### Temel Resim Kullanımı
- Resimleri, mümkün olduğunda **HTML dosyasıyla aynı klasörde** veya mantıklı bir klasör yapısı içinde (`/images` gibi) tutmak önerilir.
- Resim eklemek için `<img>` etiketi kullanılır. <br>
&nbsp; Temel yapı :
          ```
          <img src="dosya-konumu/dosya-adı.uzantı" alt="Açıklama" title="Resim Başlığı" />
          ```
> **Not:**  
> - `../` kullanarak üst klasöre çıkabiliriz. <br>
> - `src` özelliğine fotoğraf URL’i girilebilir, ancak kullanımı **önerilmemektedir**. <br>
> - `alt` her zaman eklenmeli; görme engelli kullanıcılar ve arama motorları için gereklidir.<br>
> - `title` isteğe bağlıdır, kullanıcıya ek bilgi sunar.
---

### `<img>` Etiketi Özellikleri
- `src` → Resmin dosya yolu.    
- `alt` → Resim yüklenmezse gösterilecek açıklama
  - Erişilebilirlik (accessibility) ve SEO için zorunlu kabul edilir.
- `title` → Resmin üzerine gelindiğinde görünen açıklama (isteğe bağlı)

#### Örnek Kullanım

```html
<img src="images/logo.png" alt="Site logosu" title="Ana sayfa logosu" />
```

---

### `srcset` Özelliği

- `srcset` → Tarayıcıya **aynı görselin farklı boyutlarını sunar**.
- Amaç → Cihaza göre **en uygun resmi yüklemektir.** (performans + hız)

#### Mantık

- Sen farklı boyutlarda resimler verirsin.
- Tarayıcı, ekran boyutuna göre **en uygun olanı seçer**.

### Temel Kullanım

```
<img 
  src="small.png"
  srcset="small.png 600w, medium.png 900w, big.png 1200w"
>
```

#### Açıklama

- `small.png 600w` → 600px genişliğinde resim
- `big.png 1200w` → 1200px genişliğinde resim
- `w` → width (genişlik)

#### Nasıl Çalışır?

- Tarayıcı ekranı kontrol eder.  
- En uygun genişliğe sahip resmi seçer. 
- Gereksiz büyük resmi yüklemez.  

#### `sizes` Ne Yapar?

- Resmin ekranda ne kadar yer kaplayacağını söyler.  
- Tarayıcı buna göre doğru resmi seçer.  

#### `sizes` ile Birlikte Kullanım

> **NOT**
> `src` özelliğini birlikte kullanmamızın sebebi, `srcset` desteklenmeyen eski tarayıcılarda en azından bir görselin gösterilmesini sağlamaktır. (fallback görevi görür)

```html
<img 
  src="small.png"
  srcset="small.png 600w, medium.png 900w, big.png 1200w"
  sizes="(max-width: 600px) 100vw, (max-width: 900px) 70vw, 50vw"
>
````

---

### Boyutlandırma
- `width` ve `height` HTML attribute’u olarak verilebilir; ancak modern projelerde **CSS ile boyutlandırma** önerilir.
- HTML attribute'larında birim yazılmaz, px varsayılan olarak kabul edilir.
- CSS ile boyutlandırmada ise birim zorunludur.

#### Örnek Kullanım 

```html
<img src="image.jpg" width="300" height="200" alt="Örnek görsel" />
```

>**Not:**
> Paint, Photoshop veya Figma gibi araçlarla düzenleme yapmak, sağlıklı bir yöntemdir.

---

### Saydamlık (Opacity)
- Resimlerde saydamlık (opacity) uygulanmak istendiğinde, değer **0 ile 1** arasında olmalıdır.  
  - 0 → tamamen şeffaf  
  - 1 → tamamen opak

```html
<img src="image.jpg" alt="Örnek" style="opacity: 0.5;" />
```

---

### Resim ve Metin Yerleşimi

- `<p>` etiketi içine resim ekleyip, `style="float: right"` veya `style="float: left"` ile konumlandırabiliriz.  
- Ardından `<p>` veya `<span>` içine metin yazarak resmin yanına istenilen metni yerleştirebiliriz.

#### Örnek Kullanım

```html
<p>
  <img src="images/logo.png" alt="Logo" style="float: right;">
  Bu paragraf, resmin sol tarafında yer alacak şekilde hizalanmıştır. 
  Float kullanarak resim metinle birlikte düzgün bir şekilde konumlandırılmıştır.
</p>

<p>
  <img src="images/logo.png" alt="Logo" style="float: left;">
  Bu paragraf ise resmin sağ tarafında yer alacak şekilde hizalanmıştır. 
  Margin ile resim ve metin arasında boşluk bırakılmıştır.
</p>
```

**Tarayıcı Çıktısı:**

<img width="775" height="230" alt="image" src="https://github.com/user-attachments/assets/b29d0ab7-12fb-4cc9-a279-edfed3eae78d" />

---

>**Not**
>
> Çok sayıda resim varsa `loading="lazy"` kullanarak resim sayfa açılır açılmaz değil, kullanıcı resme yaklaşınca yüklenmesi sağlanır. Varsayılan: loading="eager" (resim hemen yüklenir)
>
> `decoding="async"` varsayılan ayardır ve resmi arka planda hazırlar resim olmasa bile sayfa gösterilir.
> `decoding="sync"` sayfayı açmak için resmin yüklenmesini bekler.

### Resim Altı / Üstü Metin: `<figure>` ve `<figcaption>`

- Resimlerin altına veya üstüne açıklama eklemek istiyorsak, `<figure>` etiketi içine resmi koymalıyız.  
- Açıklamayı `<figcaption>` içine yazarız.  
  - `<figcaption>` resmin üstündeyse yazı üstte, altındaysa yazı altta görüntülenir.  
- Bu kullanım **semantiktir**, hem erişilebilirlik hem de SEO açısından avantaj sağlar.

#### Örnek Kullanım

```html
<figure>
  <img src="images/logo.png" alt="Logo" width="150">
  <figcaption>Bu resim şirket logosudur.</figcaption>
</figure>

<figure>
  <figcaption>Bu resim sitenin ana logosudur.</figcaption>
  <img src="images/logo.png" alt="Logo" width="150">
</figure>
```
**Tarayıcı Çıktısı:**

<img width="771" height="422" alt="image" src="https://github.com/user-attachments/assets/20a21bc9-04f0-42c7-b13c-4d115768e482" />

---

### Resme Tıklama Alanı Oluşturma (Image Maps)

- Bir resim üzerinde **tıklanabilir alanlar** oluşturmak için **HTML Image Maps** kullanılır.  
- `<img>` etiketi içinde `usemap="#id"` özelliği belirtilir ve tıklanabilir alanlar `<map>` etiketi ile tanımlanır. 

#### Açıklamalar

- `shape` → Tıklanabilir alanın şeklini belirtir:
  - `rect` → Dikdörtgen alan
  - `circle` → Dairesel alan
  - `poly` → Çokgen alan
  - `default` → Resmin tüm bölgesi
- `coords` → Alanın koordinatlarını belirtir (piksel cinsinden)
- `href` → Tıklanınca gidilecek bağlantı
- `alt` → Erişilebilirlik için açıklama

#### Temel Yapı

```html
<img src="dosya-konumu/dosya-adı.uzantı" alt="Açıklama" usemap="#harita1">

<map name="harita1">
  <area shape="rect" coords="x1,y1,x2,y2" href="link.html" alt="Dikdörtgen Alan">
  <area shape="circle" coords="cx,cy,r" href="link.html" alt="Dairesel Alan">
  <area shape="poly" coords="x1,y1,x2,y2,x3,y3,..." href="link.html" alt="Çokgen Alan">
  <area shape="default" href="link.html" alt="Tüm Bölge">
</map>
```

---

### Boyutlara Göre Resim Ekleme (`<picture>`)

> **NOT**
>
> `srcset` ile aralarındaki fark biri aynı resmi farklı boyutlarda göstermeyi sağlarken biri farklı resim için kullanılır.

- Farklı ekran boyutlarına göre farklı resimler göstermek için **`<picture>`** etiketi kullanılır.  
- `<source>` ile medya sorgusu ve farklı resim kaynakları belirlenir.  
- `<img>` etiketi, `<picture>` içinde varsayılan resmi gösterir.

#### Açıklamalar

- `media` → Hangi ekran boyutunda hangi resmi göstereceğimizi belirtir.
- `srcset` → Ekran boyutuna uygun resim dosyası.<br>
- `<img src>` → Varsayılan resim. (hiçbir `media` koşulu sağlanmazsa gösterilir)
- `alt` → Erişilebilirlik ve SEO için açıklama.
- `type` → Formatı belirtmeyi sağlar.

#### Örnek Kullanım

```html
<picture>
  <source media="(max-width: 600px)" srcset="images/logo-small.png" type="image/webp">
  <source media="(max-width: 1200px)" srcset="images/logo-medium.png" type="image/webp">
  <img src="images/logo-large.png" alt="Logo">
</picture>
```
---

### Önemli Noktalar
- `width` ve `height` tarayıcıya resmin orijinal boyutunu bildirir. Bu, layout shift (sayfa yüklenirken içerik kayması) sorununu önler ve aspect-ratio’yu korur.
  - `style="aspect-ratio: 4/3"` görselin en boy oranını sabit tutmayı sağlar.  
- Metinlere `alt` eklenmesi seo açısından önemlidir.
- `crossorigin = "anonymous"`: CDN veya farklı kaynaklardan yüklenen resimler için CORS problemi yaşamamak adına `img` ile beraber kullanılır. (kendi sunucundan almadığın durumlarda)
- `referrerpolicy` tarayıcının sunucuya hangi bilgiyi göndereceğini ayarlar.
  - `no-referrer` → Hiçbir referer bilgisi gönderilmez.
  - `origin` → Sadece sayfanın kök URL'sini gönderir, tam sayfa URL'sini değil.
  - `no-referrer-when-downgrade` → HTTP'den HTTPS'ye geçişte referer göndermez, aksi halde gönderir. (*Varsayılan Davranış*)

---

### Favicon

- Favicon, tarayıcı sekmesinde görünen **16x16 boyutundaki küçük simge**dir.  
- Genellikle ikinci örnek tercih edilir.

#### Açıklamalar

- `rel="icon"` → Dosyanın favicon olduğunu belirtir.
- `type` → Dosya tipini belirtir. (isteğe bağlı, önerilen yöntem)
- `href` → Favicon dosyasının konumu ve adı.
- `sizes` → Boyut ayarlamayı sağlar.

#### Örnek Kullanım

```html
<link rel="icon" href="favicon.ico">
<link rel="icon" type="image/png" sizes="32x32" href="favicon.png">
```

> **Not**
> `src` yerine `href` kullanılır; `src` yazılabilir ama **önerilmez**.

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Metin ve Biçimlendirme**](02-metin-ve-bicimlendirme.md)   
**➡️ Sonraki:** [**Ses ve Video İşlemleri**](04-ses-ve-video-işlemleri.md)
