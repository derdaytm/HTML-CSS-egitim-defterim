## Video ve Ses İşlemleri

### Desteklenen Video Formatları

HTML5, temel olarak **mp4, webm ve ogg** formatlarını destekler.

| Video Formatı | Chrome | Firefox | Safari | Edge | Opera |
|---------------|--------|---------|--------|------|-------|
| MP4           | ✅     | ✅      | ✅     | ✅   | ✅    |
| WebM          | ✅     | ✅      | ❌     | ✅   | ✅    |
| Ogg           | ✅     | ✅      | ❌     | ✅   | ✅    |
| AVI           | ❌     | ❌      | ❌     | ❌   | ❌    |
| MOV           | ❌     | ❌      | ✅     | ❌   | ❌    |

> ⚠️ HTML5 video eklemek için **mp4, webm ve ogg** önerilir.  
> Diğer formatlar tarayıcı uyumluluğu sorunları çıkarabilir.

---

### `<video>` Etiketi

Videoları HTML sayfasına eklemek için kullanılır.

> **NOT**
>
> Burada açıklamalar üzerinden anlamanız zor olacaktır. Lütfen örnekle beraber aynı anda inceleyiniz.

#### Video Özellikleri

- `src` → Video dosyasının yolu. (alternatif olarak `<source>` kullanılması önerilir)  
- `<source>` → Alternatif format belirtmek için kullanılır.  
- `controls` → Oynatma, durdurma, ses aç/kapat düğmelerini gösterir.
- `autoplay` → Sayfa açıldığında videonun otomatik oynatılmasını sağlar.  
- `loop` → Videonun sürekli oynatılmasını sağlar.  
- `muted` → Videonun sesi kısık başlar. 
- `preload` → Tarayıcı sayfa yüklenirken videonun ne kadarını önceden yükleyeceğini belirler:
  - `none` → indirmez.  
  - `metadata` → sadece meta veriyi indirir.  
  - `auto` → tamamen veya bir kısmını indirir.  
- `poster` → Video yüklenmeden önce gösterilecek görsel.
- `width` → Videonun genişliğini belirler. (piksel cinsinden)  
- `height` → Videonun yüksekliğini belirler. (piksel cinsinden)
- `track` → Video için altyazı ekler.
  - `srclang` → Altyazı dilini belirtir.
  - `label` → Kullanıcıya gösterilecek altyazı adını belirtir.
- `kind` özniteliği, `<track>` ile eklenen içeriğin türünü belirtir. Desteklenen değerler ve açıklamaları:
  - **subtitles** → Video veya sesin konuşmalarını farklı bir dilde altyazı olarak sağlar.  
    _Örnek:_ Türkçe altyazı eklemek için kullanılır.
  - **captions** → Video veya sesin konuşmalarını aynı dilde, işitme engelliler için metin olarak gösterir.  
    _Örnek:_ İngilizce videoda İngilizce altyazı, işitme engelliler için.
  - **descriptions** → Videodaki görsel öğeleri açıklayan metin ekler.  
    _Örnek:_ Görsel anlatım eksikliği olan kullanıcılar için, sahne açıklamaları.
  - **chapters** → Video bölümlerini tanımlamak için kullanılır; video oynatıcısında bölüm atlama gibi işlev sağlar.  
    _Örnek:_ 0:00-2:30 → Giriş, 2:30-5:00 → Ana bölüm
  - **metadata** → Videoya veya ses dosyasına bağlı ek bilgileri (meta veri) taşır, kullanıcıya gösterilmez.  
    _Örnek:_ Alt yazı senkronizasyon bilgisi veya ekstra veri dosyaları.
  - default ile birden fazla altyazı olduğu durumlarda varsayılan ayarı seçmeyi sağlar.

#### Gelişmiş Video Özellikleri
- `crossorigin = "anonymous"`
  - Eğer videoyu **CDN’den veya farklı bir kaynaktan** çekiyorsanız, `crossorigin` özelliği gerekli olabilir.
  - Amaç: Tarayıcıların **CORS (Cross-Origin Resource Sharing)** politikaları nedeniyle video verisine erişim ve işlem yapılabilmesini sağlamak.

- `playsinline`
  - Mobil cihazlarda videonun **tam ekran yerine sayfa içinde** oynatılmasını sağlar.
  - Önerilen kullanım, özellikle **iOS Safari** gibi tarayıcılarda otomatik oynatma ve kullanıcı deneyimi için önemlidir.

#### Örnek Kullanım

```html
<video 
    src="video.mp4"
    width="640" 
    height="360" 
    controls 
    autoplay 
    loop 
    muted 
    preload="auto" 
    poster="video-poster.jpg">
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <track src="altyazi-tr.vtt" kind="subtitles" srclang="tr" label="Türkçe">
  Tarayıcınız video etiketini desteklemiyor.
</video>
```

**Tarayıcı Çıktısı:**

<img width="771" height="392" alt="image" src="https://github.com/user-attachments/assets/582810d0-0b8a-4f47-8d18-8003f6b16194" />

---

### `<audio>` Etiketi

Ses dosyalarını HTML sayfasına eklemek için kullanılır.

> **NOT**
>
> Burada açıklamalar üzerinden anlamanız zor olacaktır. Lütfen örnekle beraber aynı anda inceleyiniz.

#### `<audio>` Etiketi Özellikleri

- `src` → Ses dosyasının yolu. (alternatif olarak `<source>` kullanılması önerilir)  
- `<source>` → Alternatif format belirtmek için kullanılır.  
- `controls` → Oynatma, durdurma, ses aç/kapat düğmelerini gösterir. 
- `autoplay` → Sayfa açıldığında sesin otomatik oynatılmasını sağlar.  
- `loop` → Sesin sürekli oynatılmasını sağlar.  
- `muted` → Ses başlangıçta kapalı olur.  
- `type` → Ses dosyasının türünü belirtir. (örn. `audio/mpeg`, `audio/ogg`)
- `preload` → Tarayıcı sayfa yüklenirken sesin ne kadarını önceden indirir:
  - `none` → indirmez.  
  - `metadata` → sadece meta veriyi indirir.  
  - `auto` → tamamen veya bir kısmını indirir.
- `track` → Ses için altyazı ekler.
- `kind` özniteliği, `<track>` ile eklenen içeriğin türünü belirtir. Desteklenen değerler ve açıklamaları:
  - **subtitles** → Video veya sesin konuşmalarını farklı bir dilde altyazı olarak sağlar.  
    _Örnek:_ Türkçe altyazı eklemek için kullanılır.
  - **captions** → Video veya sesin konuşmalarını aynı dilde, işitme engelliler için metin olarak gösterir.  
    _Örnek:_ İngilizce videoda İngilizce altyazı, işitme engelliler için.
  - **descriptions** → Videodaki görsel öğeleri açıklayan metin ekler.  
    _Örnek:_ Görsel anlatım eksikliği olan kullanıcılar için, sahne açıklamaları.
  - **chapters** → Video bölümlerini tanımlamak için kullanılır; video oynatıcısında bölüm atlama gibi işlev sağlar.  
    _Örnek:_ 0:00-2:30 → Giriş, 2:30-5:00 → Ana bölüm
  - **metadata** → Videoya veya ses dosyasına bağlı ek bilgileri (meta veri) taşır, kullanıcıya gösterilmez.  
    _Örnek:_ Alt yazı senkronizasyon bilgisi veya ekstra veri dosyaları.
  - default ile birden fazla altyazı olduğu durumlarda varsayılan ayarı seçmeyi sağlar.

#### Gelişmiş Video Özellikleri
- `crossorigin = "anonymous"`
  - Eğer videoyu **CDN’den veya farklı bir kaynaktan** çekiyorsanız, `crossorigin` özelliği gerekli olabilir.
  - Amaç: Tarayıcıların **CORS (Cross-Origin Resource Sharing)** politikaları nedeniyle video verisine erişim ve işlem yapılabilmesini sağlamak.

- `playsinline`
  - Mobil cihazlarda videonun **tam ekran yerine sayfa içinde** oynatılmasını sağlar.
  - Önerilen kullanım, özellikle **iOS Safari** gibi tarayıcılarda otomatik oynatma ve kullanıcı deneyimi için önemlidir.

#### Örnek Kullanım

```html
<audio 
    src="audio.mp3" 
    controls 
    autoplay 
    loop 
    muted
    preload="auto">
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  <track src="altyazi-tr.vtt" kind="subtitles" srclang="tr" label="Türkçe">
  Tarayıcınız audio etiketini desteklemiyor.
</audio>
```

**Tarayıcı Çıktısı:**

<img width="775" height="62" alt="image" src="https://github.com/user-attachments/assets/0ed19fdf-bd0d-4263-b30f-59fa732cfdac" />

---

### Önemli Noktalar

- **Her zaman birden fazla format ekleyin:**  
  `<source>` kullanımı kritik, tarayıcı uyumluluğunu artırır. <br>
  Desteklenmemesi durumuna karşı metin ekleyin.

- **Poster** sadece `<video>` etiketi için geçerlidir; videodan önce gösterilecek resmi belirtir.

- **Boyutlandırma:**
  - Sadece videoda geçerlidir.
  - `width` ve `height` HTML attribute'larında **piksel cinsinden** verilmelidir.  
  - Modern projelerde **CSS ile boyutlandırma** tercih edilir.

- **Autoplay ve Muted kombinasyonu:**  
  - Mobil tarayıcılarda sesli otomatik oynatma çoğu zaman engellenir.  
  - Bu nedenle, video başlangıçta sessiz (muted) olmalı ve autoplay ile birlikte kullanılmalıdır.
 
---

## Eski / Alternatif Medya Etiketleri: `<object>` ve `<embed>`

### `<object>` Etiketi
- HTML sayfasına PDF, Flash veya diğer medya türlerini eklemek için kullanılır.
- İçerik yüklenmezse **alternatif içerik** gösterilebilir. (semantik ve erişilebilir).
- **Özellikler:**
  - `data` → İçeriğin kaynağı
  - `type` → İçeriğin MIME türü
  - `width` ve `height` → Boyutlandırma (piksel cinsinden)

#### Örnek Kullanım

```html
<object data="example.pdf" type="application/pdf" width="600" height="400">
  <p>Tarayıcınız PDF dosyalarını desteklemiyor. <a href="example.pdf">İndir</a>.</p>
</object>
```

**Tarayıcı Çıktısı:**

<img width="775" height="39" alt="image" src="https://github.com/user-attachments/assets/8a4281a7-94a7-47cf-a4a0-627a7a0325a9" />

---

### `<embed>` Etiketi

HTML sayfasına medya veya eklenti tabanlı içerik gömmek için kullanılır.  

> **Not:** Alternatif içerik göstermez; tarayıcı desteklemezse boş alan kalır.

### Özellikler
- `src` → İçeriğin kaynağı
- `type` → İçeriğin MIME türü
- `width` ve `height` → Boyutlandırma (piksel cinsinden)

### Örnek Kullanım

```html
<embed src="example.pdf" type="application/pdf" width="600" height="400">
```

**Tarayıcı Çıktısı:**

<img width="771" height="437" alt="image" src="https://github.com/user-attachments/assets/966074ba-3749-45b3-b368-e91c825d6c92" />

---

### `<object>` ve `<embed>` Farkları

| Özellik               | `<object>`                          | `<embed>`                       |
|-----------------------|-----------------------------------|---------------------------------|
| Desteklenen içerik     | PDF, Flash, medya türleri           | Medya ve eklenti tabanlı içerikler |
| Alternatif içerik      | Evet                               | Hayır                           |
| Esneklik               | Yüksek                             | Daha basit                      |
| Kullanım               | PDF, Flash, diğer medya türleri     | Video, ses, eklenti tabanlı içerikler |

> **Not:**  
> Günümüz projelerinde video için `<video>`, ses için `<audio>`, PDF için JS tabanlı çözümler veya `<iframe>` kullanmak daha yaygındır.  
> `<object>` ve `<embed>` genellikle eski veya özel durumlar için tercih edilir.

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Görseller ve Resim İşlemleri**](03-görseller-ve-resim-işlemleri.md)   
**➡️ Sonraki:** [**Tablo ve Liste İşlemleri**](05-tablo-ve-liste-işlemleri.md)
