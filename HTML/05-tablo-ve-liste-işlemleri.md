## Tablo İşlemleri

> **NOT**
>
> Burada açıklamalar üzerinden anlamanız zor olacaktır. Lütfen örnekle beraber aynı anda inceleyiniz.

- `<table>` → Tablo oluşturmak için ana etikettir.  
  - `caption` → Tablo başlığı ekler, `<table>` etiketinin hemen altına yazılır. (*Semantik olarak avantajlıdır*)
  - `width` → Tablo genişliğini belirler. (modern projelerde CSS ile verilmesi önerilir).  
  - `border` → Tablo kenarlık kalınlığı. (CSS kullanımı önerilir).  
  - `cellspacing` → Hücreler arası boşluğu HTML attribute ile belirler.
- `<colgroup>` → Tablo sütunlarını gruplamak için kullanılır.
- `<col>` → Tek tek sütunlar üzerinde stil ve genişlik vermek için kullanılır.  
- `<tr>` → Tablo satırı oluşturur.  
- `<td>` → Tablo hücresi oluşturur.  
  - `headers` → Bu hücrenin hangi `<th>` ile ilişkili olduğunu belirtir. (karmaşık tablolar için).  
- `<th>` → Tablo başlık hücresi oluşturur.  
  - `scope` → Başlık hücresinin kapsamını belirtir. (`col`, `row`).  
- `<thead>` → Tablo başlık bölümünü tanımlar.  
- `<tbody>` → Tablo veri bölümünü tanımlar.  
- `<tfoot>` → Tablo alt bölümünü tanımlar.  
- `colspan` → Satırdaki hücreleri birleştirir. (`<td>` veya `<th>` içinde kullanılır).  
- `rowspan` → Sütundaki hücreleri birleştirir. (`<td>` veya `<th>` içinde kullanılır).  

### Erişilebilirlik (ARIA) Etiketleri

- `aria-label` → Tabloya kısa bir açıklama ekler; kullanıcıya sadece ekran okuyucu aracılığıyla görünür.  
- `aria-describedby` → Tabloyla ilgili daha uzun bir açıklama veya referans belirtir; genellikle başka bir öğeye işaret eder ve ekran okuyucuda tabloyla ilişkilendirilir.  

### Ek HTML Yapıları

- `<details>` → Gizli içerik eklemek için kullanılır; kullanıcı tıkladığında açılır.  
- `<summary>` → `<details>` içinde başlık olarak görünür ve tıklanabilir alan sağlar.  

> Not: `summary` ve `details` doğrudan tablo etiketi ile ilgili değildir ama tablo verisini açıklayıcı veya katlanabilir bilgi eklemek için kullanılabilir.

### Örnek Kullanım

```html
<table 
  width="100%"      <!-- Tablo genişliği, modern projelerde CSS ile verilmesi önerilir -->
  border="2"        <!-- Tablo kenarlık kalınlığı, modern projelerde CSS ile verilmesi önerilir -->
  cellspacing="10"  <!-- Hücreler arası boşluk, modern projelerde border-spacing ile CSS kullanılır -->
  aria-label="Çalışan Listesi Tablosu" 
  aria-describedby="tabloAciklama"
>
  <caption>Çalışan Listesi</caption>

 <!-- Sütun grubu ve sütun genişlikleri -->
  <colgroup>
    <col span="1" width="50">   <!-- 1. sütun genişliği 50 piksel -->
    <col span="2" width="150">  <!-- 2. ve 3. sütun genişliği 150 piksel -->
    <col span="1" width="100">  <!-- 4. sütun genişliği 100 piksel -->
  </colgroup>

  <thead>
    <tr>
      <th scope="col">ID</th>
      <th scope="col">Ad</th>
      <th scope="col">Soyad</th>
      <th scope="col">Departman</th>
      <th scope="col">Görev</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td rowspan="2" headers="ID">1</td>
      <td headers="Ad">Ahmet</td>
      <td headers="Soyad">Yılmaz</td>
      <td>İK</td>
      <td>Uzman</td>
    </tr>
    <tr>
      <td>Ayşe</td>
      <td>Kara</td>
      <td>İK</td>
      <td>Stajyer</td>
    </tr>
    <tr>
      <td>2</td>
      <td colspan="2">Mehmet Demir</td>
      <td>Finans</td>
      <td>Müdür</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td colspan="5">Toplam Çalışan: 4</td>
    </tr>
  </tfoot>
</table>

<p id="tabloAciklama">
  Bu tablo şirket çalışanlarını ve görevlerini göstermektedir.
</p>

<details>
  <summary>Tablo Kullanım Açıklamaları</summary>
  <p>
    Bu tablo örneği rowspan, colspan, ARIA etiketleri, width, border ve cellspacing kullanımını göstermektedir.
  </p>
</details>
```

**Tarayıcı Çıktısı:**

<img width="777" height="320" alt="image" src="https://github.com/user-attachments/assets/bb8efb72-39b5-44c3-8294-4508adff040a" />

---

## Liste İşlemleri

- `<ol>` → Numaralı liste oluşturmak için kullanılır.
  - `start="x"` → Listenin hangi sayıdan başlayacağını belirler.
  - `reversed="reversed"` → Listenin artan yerine azalan şekilde sıralanmasını sağlar.
  - `type="x"` → Liste işaretlerini değiştirir:
    - `A` → Büyük harflerle sıralar.
    - `a` → Küçük harflerle sıralar.
    - `I` → Roma rakamıyla sıralar.
    - `i` → Küçük Roma rakamıyla sıralar.
    - `1` → Sayısal. (varsayılan)
- `<ul>` → Numarasız liste oluşturmak için kullanılır. Menü veya normal listelerde kullanılır.
  - `type="x"` → Marker (işaret) tipini değiştirir. (HTML5 ile bazı tipler tarayıcıya bağlıdır, CSS ile değiştirmek daha yaygın):
    - `disc` → Dolu daire. (varsayılan)
    - `circle` → Boş daire.
    - `square` → Dolu kare.
    - `none` → İşaret kaldırılır.
> **Not**:
> `<ul>` için `list-style-type` kullanarak CSS ile de değiştirilebilir; özel marker kullanımı CSS ile daha esnektir.
- `<li>` → Liste elemanlarını gösterir.
  - `value="x"` → Tek tek `<ol>` elemanının numarasını değiştirmek için kullanılır.

### Örnek Kullanım
```html
<!-- Numaralı Liste Örneği -->
<ol start="3" type="A" reversed="reversed">
  <li>İlk eleman</li>
  <li value="10">İkinci eleman (numara 10 olarak değiştirildi)</li>
  <li>Üçüncü eleman</li>
</ol>

<!-- Numarasız Liste Örneği -->
<ul type="square">
  <li>Elma</li>
  <li>Armut</li>
  <li>Kiraz</li>
</ul>

<ul type="circle">
  <li>Python</li>
  <li>JavaScript</li>
  <li>HTML & CSS</li>
</ul>

<ul type="none">
  <li>Liste işareti yok</li>
  <li>Bir diğer madde</li>
</ul>
```

**Tarayıcı Çıktısı:**

<img width="775" height="280" alt="image" src="https://github.com/user-attachments/assets/4381de17-a43f-4b0a-b56b-6e90eac14a87" />

### Tanımlama listeleri: `<dl>, <dt>, <dd>`

- `<dl>` → Tanımlama listesini oluşturur.
- `<dt>` → Listelenen nesneyi belirtir.
- `<dd>` → Nesnenin açıklamasını içerir.

> Birden fazla `<dt>` ve `<dd>` kullanılabilir; her `<dt>` için bir veya birden fazla `<dd>` olabilir.

> **Not**:
> HTML attribute ile listelerin tipi ve sıralama kontrol edilebilir, ancak modern projelerde genellikle CSS ile stil ve marker değiştirme tercih edilir.

### Örnek Kullanım
```html
<dl>
  <dt>HTML</dt>
  <dd>Web sayfalarının yapısını oluşturmak için kullanılan işaretleme dili.</dd>
  <dd>Tarayıcılar tarafından yorumlanır ve görselleştirilir.</dd>

  <dt>CSS</dt>
  <dd>Web sayfalarının görünümünü ve stilini belirlemek için kullanılır.</dd>

  <dt>JavaScript</dt>
  <dd>Web sayfalarına etkileşim ve dinamik davranış eklemek için kullanılan programlama dili.</dd>
  <dd>Form doğrulama, animasyon ve API çağrıları gibi işlemler için kullanılır.</dd>
</dl>
```

**Tarayıcı Çıktısı:**

<img width="773" height="167" alt="image" src="https://github.com/user-attachments/assets/ebfc6b88-ea97-4f02-aef2-18d175d2a286" />

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Ses ve Video İşlemleri**](04-ses-ve-video-işlemleri.md)   
**➡️ Sonraki:** [**Link İşlemleri**](06-link-işlemleri.md)
