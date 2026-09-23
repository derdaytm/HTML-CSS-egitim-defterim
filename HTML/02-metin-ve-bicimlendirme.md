## Metin Özellikleri

> **NOT :**  
> **Semantik** → Anlam taşıyan, SEO ve erişilebilirliği destekleyen etiketler.  
> **Semantik değil** → Yalnızca görsel amaçlı kullanılan etiketler.

---

### Satır ve Paragraf

- `<p>` → Paragraf oluşturur. *(Semantik)*
- `<br />` → Satır atlamayı sağlar, kapanış etiketi yoktur. *(Semantik değil)*
- `<wbr />` → Satıra sığmayan kelimelerin uygun yerden alt satıra geçmesini sağlar. *(Semantik değil - Özel durumlarda kullanılır)*

#### Örnek Kullanım :

```html
<p>Bu bir paragraftır.</p>

<p>
HTML ile yazılan metinler varsayılan olarak aynı satırda devam eder.
<br />
Bu satır, br etiketi sayesinde alt satıra geçmiştir.
</p>

<p>
Uzun kelimeler ekrana sığmadığında taşma yapabilir. Buna örnek verecek olursak :
supercalifragilistic<wbr />expialidocious
kelimesi uygun yerden bölünebilir.
</p>
```

**Tarayıcı Çıktısı:**

<img width="774" height="146" alt="image" src="https://github.com/user-attachments/assets/aa136169-ff3d-4da1-963a-d8297df70525" />


---

### Başlıklar

- `<h1>` – `<h6>` → Başlık etiketleridir.  (Semantik)
  - Sayılar 1’den 6’ya kadar gider.  
  - Hiyerarşik yapıdadır ve sırayla kullanılması semantik açıdan daha faydalıdır.  
  - `h1` en büyük başlıktır. 
  - `h6` en küçük başlıktır. 
- `<hgroup>` → Başlıkları gruplamak için kullanılır. *(Semantik - Nadiren kullanılır)*

#### Örnek Kullanım :

```html
<hgroup>
  <h1>HTML Öğreniyorum</h1>
  <h2>Başlık Etiketleri</h2>
</hgroup>

<h3>Alt Başlık</h3>
<h4>Daha Küçük Başlık</h4>
<h5>Küçük Başlık</h5>
<h6>En Küçük Başlık</h6>
```

**Tarayıcı Çıktısı:**

<img width="773" height="264" alt="image" src="https://github.com/user-attachments/assets/267ad53a-4901-42ae-821c-4e7195d3cbb5" />


---

### Vurgu ve Biçimlendirme

- `<b>` → Metni kalın yapar. *(Semantik değil)*
- `<strong>` → Metni kalın yapar, anlamsal vurgu içerir. *(Semantik)*
- `<i>` → Metni eğik yapar. *(Semantik değil)*
- `<em>` → Metni eğik yapar, anlamsal vurgu içerir. *(Semantik)*
- `<u>` → Metnin altını çizer. *(Semantik değil)*
- `<ins>` → Sonradan eklenen metni belirtir, altı çizilir. *(Semantik)*
- `<del>` → Metnin üzerini çizer. Metnin dokümandan silindiğini veya değiştirildiğini ifade eder. *(Semantik)*
- `<s>` → Metnin üzerini çizer. İçeriğin artık geçerli veya doğru olmadığını ifade eder. *(Semantik)*
- `<strike>` → Metnin üzerini çizer. (Kullanımdan kaldırılmıştır) *(Semantik değil)*
- `<mark>` → Metni fosforlu kalemle işaretlenmiş gibi gösterir. Vurgulama amaçlı kullanılır. *(Semantik)*
- `<small>` → Daha küçük yazı gösterir. *(Semantik değil)*
- `<hr />` → Satır çizgisi çeker. *(Semantik)*

#### Örnek Kullanım :

```html
<b>Kalın metin</b><br>
<strong>Önemli metin</strong><br>
<i>Eğik metin</i><br>
<em>Vurgulu eğik metin</em><br>
<u>Altı çizili metin</u><br>
<ins>Sonradan eklenen metin</ins><br>
<del>Silinmiş metin</del><br>
<s>Silinmiş metin</s><br>
<strike>Silinmiş metin</strike> <br>
<mark>Vurgulanan metin</mark><br>
<small>Küçük metin</small>
<hr />
```

**Tarayıcı Çıktısı:**

<img width="468" height="218" alt="image" src="https://github.com/user-attachments/assets/28673e58-e326-43f8-a6d9-59515c0933a5" />

---

### Alıntılar ve Kaynaklar

- `<cite>` → Kaynak veya alıntıyı belirtmek için kullanılır. Vurgulanan yer eğik yazılır. *(Semantik)*
- `<blockquote>` → Uzun alıntılar için kullanılır. *(Semantik)*  
  - Satır içi kaynak ve alıntı belirtmek için `<cite>` kullanılabilir.
- `<q>` → Kısa alıntılar için kullanılır, tarayıcı otomatik tırnak ekler. *(Semantik)*

#### Örnek Kullanım :

```html
<p>
  <cite>Albert Einstein</cite> şöyle demiştir:
  <q>Hayal gücü bilgiden daha önemlidir.</q>
</p>

<blockquote>
  <p>
    Hayal gücü bilgiden daha önemlidir. Çünkü bilgi sınırlıdır,
    hayal gücü ise tüm dünyayı kapsar.
  </p>
  <cite>Albert Einstein</cite>
</blockquote>
```

**Tarayıcı Çıktısı:**

<img width="776" height="106" alt="image" src="https://github.com/user-attachments/assets/46cd5191-bc97-42e3-a8e3-8c7ce1be277f" />

---

### Tanım ve Açıklamalar

- `<abbr>` → Kısaltmalar için kullanılır. *(Semantik)*  
  - `title` özelliği ile açılım belirtilir.
- `<dfn>` → Tanımı yapılan terimi belirtir. *(Semantik)*

#### Örnek Kullanım :

```html
<p>
  <abbr title="Hyper Text Markup Language">HTML</abbr> web sayfalarının
  yapısını oluşturmak için kullanılır.
</p>

<p>
  <dfn>SEO</dfn>, arama motorları için web sitelerinin
  optimize edilmesi sürecidir.
</p>
```

**Tarayıcı Çıktısı:**

<img width="774" height="73" alt="image" src="https://github.com/user-attachments/assets/07abb012-a23d-46ad-979a-228a92b8ec82" />

---

### Üst / Alt Simge

- `<sup>` → Üst simge oluşturur. *(Semantik değil)*
- `<sub>` → Alt simge oluşturur. *(Semantik değil)*

#### Örnek Kullanım :

```html
<p>
  Matematikte üslü sayılar: 2<sup>3</sup> = 8
</p>

<p>
  Kimyada suyun formülü: H<sub>2</sub>O
</p>
```

**Tarayıcı Çıktısı:**

<img width="775" height="73" alt="image" src="https://github.com/user-attachments/assets/85b71155-cc1b-449c-b0ae-5ea266554841" />

---

### Kod ve Teknik İçerik

- `<code>` → Kod, dosya adı, program ismi veya program kodu belirtmek için kullanılır. *(Semantik)*
- `<kbd>` → Klavyeden girilmesi gereken girdileri belirtir. *(Semantik)*
- `<samp>` → Program çıktısını belirtir. *(Semantik)*
- `<var>` → Matematiksel veya programlama değişkenlerini belirtir. *(Semantik)*
- `<pre>` → İçeriği yazıldığı biçimde gösterir. Genelde vurgu yapmak veya alıntı yapılan metinlerde kullanılır. *(Semantik değil)*

#### Örnek Kullanım :

```html
<p>
  Dosyayı <code>index.html</code> olarak kaydedin.
</p>

<p>
  Programı çalıştırmak için <kbd>Ctrl</kbd> + <kbd>C</kbd> tuşlarına basın.
</p>

<p>
  Program çıktısı: <samp>İşlem başarıyla tamamlandı</samp>
</p>

<p>
  Formülde <var>x</var> bilinmeyen değeri temsil eder.
</p>

<pre>
function hello() {
  console.log("Merhaba Dünya");
}
</pre>
```

**Tarayıcı Çıktısı:**

<img width="774" height="213" alt="image" src="https://github.com/user-attachments/assets/52778915-c684-49fe-848b-fff392754745" />

---

### Genel Amaçlı Etiketler

- `<span>` → Satır içi metinleri seçmek ve CSS ile stil vermek için kullanılır. *(Semantik değil)*
- `<address>` → Belgenin yazarına ait iletişim bilgilerini belirtir. *(Semantik)*

#### Örnek Kullanım :

```html
<p>
  Bu cümlede <span style="color: red;">önemli</span> bir kelime vurgulanmıştır.
</p>

<address>
  Yazar: Ahmet Yılmaz <br>
  E-posta: ahmet@example.com <br>
  Web sitesi: www.example.com
</address>
```

**Tarayıcı Çıktısı:**

<img width="778" height="99" alt="image" src="https://github.com/user-attachments/assets/3f44bb39-9949-4951-b0f7-555afa66774a" />

---

### Zaman ve Dil Odaklı Etiketler

- `<time>` → Tarih ve saat bilgisini semantik olarak belirtmek için kullanılır. *(Semantik)*  
  - Makine tarafından okunabilir zaman verisi sağlar.  
  - SEO ve erişilebilirliği destekler.

#### Örnek Kullanım :

```html
<p>
  Bu doküman 
  <time datetime="2026-01-08">8 Ocak 2026</time>
  tarihinde oluşturulmuştur.
</p>
```

**Tarayıcı Çıktısı:**

<img width="775" height="35" alt="image" src="https://github.com/user-attachments/assets/8720eccb-11b8-4f2e-85f2-60254b8321d9" />

---

### Metin Yönü ve Çok Dilli İçerik

- `<bdi>` → Metin yönünü çevresinden izole eder.  
  - Çok dilli ve dinamik içeriklerde kullanılır. *(Semantik)*
- `<bdo>` → Metnin yazım yönünü zorla belirler (`ltr`, `rtl`). *(Semantik)*  
  - Sağdan sola yazılan diller için kullanılır.
 
#### Örnek Kullanım :

```html
<p>
  Kullanıcı adı: <bdi>علي</bdi>
</p>
<p>
  <bdo dir="rtl">Merhaba Dünya</bdo>
</p>
```

**Tarayıcı Çıktısı:**

<img width="779" height="66" alt="image" src="https://github.com/user-attachments/assets/ed5afc6c-8462-4566-99bc-beb193b8fe11" />

---

### Özel Dil Yapıları

- `<ruby>` → Doğu Asya dillerinde (Japonca, Çince vb.) telaffuz açıklamaları için kullanılır. *(Semantik)*  
  - `<rt>` ve `<rp>` etiketleriyle birlikte kullanılır.
  - Çoğu projede gerekmez, özel durumlara yöneliktir.
 
#### Örnek Kullanım :

```html
<p>
  <ruby>
    漢字
    <rp>(</rp>
    <rt>Kanji</rt>
    <rp>)</rp>
  </ruby>
</p>
```

**Tarayıcı Çıktısı:**

<img width="776" height="39" alt="image" src="https://github.com/user-attachments/assets/4a571fa3-eef0-4e63-b821-9faffc66df50" />

---

### Kullanımı Kaldırılan Etiket

- `<font>` → Metin biçimlendirmek için kullanılırdı.  
  - HTML5 ile **kaldırılmıştır**.
  - Yerine **CSS** kullanılmalıdır.

### `<font>` ve CSS Karşılaştırması

| Özellik | `<font>` ile | CSS ile |
|------|-------------|--------|
| Renk | `color="red"` | `style="color: red;"` |
| Arka plan rengi | Yok | `style="background-color: yellow;"` |
| Yazı boyutu | `size="5"` | `style="font-size: 20px;"` |
| Yazı tipi | `face="Arial"` | `style="font-family: Arial;"` |
| Hizalama | `align="center"` | `style="text-align: center;"` |

#### Örnek Kullanım :

```html
```html
<font color="red" size="5" face="Arial">
  Bu metin eski font etiketi ile yazılmıştır.
</font>
```

**Tarayıcı Çıktısı:**

<img width="774" height="33" alt="image" src="https://github.com/user-attachments/assets/c386f6c1-05ef-437f-a5ac-93583a189302" />

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Temel Bilgiler**](01-temel-bilgiler.md)  
**➡️ Sonraki:** [**Görseller ve Resim İşlemleri**](03-görseller-ve-resim-işlemleri.md)  
