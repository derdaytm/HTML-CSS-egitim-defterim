### Kutu Modeline Giriş
Her HTML elementi birer kutucuk (box) gibi düşünülebilir. Bu kutuların içeriği, iç boşluğu (padding), kenarlık çizgisi (border) ve dış boşluğu (margin) vardır. Bu parametreler sayesinde elementlerin sayfa içindeki boyutu ve konumu belirlenir.

<img width="767" height="420" alt="image" src="https://github.com/user-attachments/assets/9a6a757c-da09-45ec-a650-edc9b5bb7ce5" />      <br>

CSS kutu modeline geçmeden önce bilmemiz gereken bir konu: bazı HTML elementleri block, bazıları inline olarak çalışır. Bu davranış elementin sayfadaki yerleşimini ve kutu modelini etkiler.    
  - Block
    -  Block elementler, **yeni satırdan başlar**, tüm genişliği kaplar ve kendi satırını oluşturur.
    -  Özellikler :
      -  `width` ve `height` değerleri atanabilir.
      -  `margin` ve `padding` ile tüm kenarlarda boşluk uygulanabilir.
    - Örnekler : `div` - `p` - `h1 - h6` - `section` - `header` - `footer` vb.

  - İnline
    - İnline elementler, **aynı satırda yan yana** durur ve yalnızca içerik kadar genişlik kaplar.
      - Özellikler :
        - `width` ve `height` genellikle çalışmaz.
        - Sadece **yatay boşluklar** (`padding-left`,`padding-right`,`margin-left`,`margin-right`) uygulanabilir.
        - Dikey boşluk (`padding-top`,`padding-bottom`,`margin-top`,`margin-bottom`) etkisi sınırlıdır.
      - Örnekler : `span` - `a` - `strong` - `em` - `img` vb.

<img width="468" height="401" alt="image" src="https://github.com/user-attachments/assets/73cb46e1-3d72-4bc5-a92e-c2934b9fa00a" />    <br>

> **NOT :**
>
> Block ve inline davranışları `display` özelliğiyle değiştirebiliriz. Ayrıca block elemanlarının içinde inline elemanlarda bulunabilir.
> Ayrıca `display: flex` özelliği ile kutuyu esnek hale getirebiliriz.(içindeki kutuları esnek bir şekilde hizalar ve yerleştirir) 

```css
span {
  display: block;
}

div {
  display: inline;
}

.container {
  display: flex;
}
```

---

### `Width` / `Height` / `Max` / `Min` `Width-Height`
- `width` → Bir elementin **genişliğini** belirler.
- `height` → Bir elementin **yüksekliğini** belirler.
- `max-width` → Elementin ulaşabileceği **en büyük genişliği** belirler.
- `max-height` → Elementin ulaşabileceği **en büyük yüksekliği** belirler.
- `min-width` → Elementin küçülebileceği **en küçük genişliği** belirler.
- `min-height` → Elementin küçülebileceği **en küçük yüksekliği** belirler.

Bu özellikler özellikle responsive tasarımda elementlerin çok büyümesini veya çok küçülmesini engellemek için kullanılır.

**Örnek Kullanım :**
```css
div.box {
    width: 400px;
    height: 200px;
}

img {
    max-width: 100%;
    height: auto;
}

.container {
    min-width: 300px;
    max-width: 900px;
}

.card {
    min-height: 150px;
    max-height: 400px;
}
```

> Bu sayede elementler **farklı ekran boyutlarında** kontrol altında tutulabilir.

---

### `Padding`, `Border` ve `Margin`
- `Padding` (İç Boşluk)
  - İçerik ile kenarlık(border) arasındaki boşluğu ayarlar.
  - Yani kutunun **iç tarafındaki boşluğu** belirler.
  - İçeriğin kenarlığa yapışmasını engellemek için kullanılır.

- `Border` (Kenarlık)
  - Elementin **etrafına bir çerçeve(kenarlık)** ekler.
  - Kenarlığın **kalınlığının türü ve rengi** belirlenir.
 
- `Margin` (Dış Boşluk)
  - Bir elementin diğer elementlerle arasındaki dış boşluğu ayarlar.
  - Yani kutunun dış tarafındaki mesafeyi belirler.

> `%`, `em`, `vw`, `vh` gibi ölçü birimlerini kullanabilirsiniz.     
 
Padding (İç Boşluk)
| Özellik | Açıklama | Örnek |
|---|---|---|
| `padding` | Üst, sağ, alt ve sol boşluk için **aynı değeri** belirler. | `padding: 20px;` |
| `padding: üst sağ alt sol` | Üst, sağ, alt ve sol boşluk için **farklı değerler** belirler. | `padding: 10px 20px 15px 5px;` |
| `padding: (üst-alt) (sağ-sol)` | Üst–alt ve sağ–sol boşlukları için **iki farklı değer** belirler. | `padding: 10px 20px;` |
| `padding-top` | Sadece **üst boşluğu** belirler. | `padding-top: 15px;` |
| `padding-right` | Sadece **sağ boşluğu** belirler. | `padding-right: 20px;` |
| `padding-bottom` | Sadece **alt boşluğu** belirler. | `padding-bottom: 15px;` |
| `padding-left` | Sadece **sol boşluğu** belirler. | `padding-left: 20px;` |


Border (Kutu Kenarlıkları)
| Özellik | Değerler | Açıklama |
|---|---|---|
| `border-style` | none, solid, dotted, dashed, double, groove, ridge, inset, outset | Çizgi türünü belirler. |
| `border-top-style`, `border-right-style`, `border-bottom-style`, `border-left-style` | border-style değerleriyle aynı | Belirli kenarın çizgi tipini ayarlar. |
| `border-width` | ölçü birimleri, thin, medium, thick | Kenarlık kalınlığı. |
| `border-top-width`, `border-right-width`, `border-bottom-width`, `border-left-width` | ölçü birimleri, thin, medium, thick | Belirli kenarın kalınlığını ayarlar. |
| `border-color` | Renk adı, #rrggbb, rgb(rrr,ggg,bbb) | Kenarlık rengini belirler. |
| `border-top-color`, `border-right-color`, `border-bottom-color`, `border-left-color` | border-color değerleriyle aynı  | Belirli kenarın rengini ayarlar. |


Margin (Dış Boşluk)
| Özellik | Açıklama | Örnek |
|---|---|---|
| `margin` | Üst, sağ, alt ve sol boşluk için **aynı değeri** belirler. | `margin: 20px;` |
| `margin: üst sağ alt sol` | Üst, sağ, alt ve sol boşluk için **farklı değerler** belirler. | `margin: 10px 20px 15px 5px;` |
| `margin: (üst-alt) (sağ-sol)` | Üst–alt ve sağ–sol boşlukları için **iki farklı değer** belirler. | `margin: 10px 20px;` |
| `margin-top` | Sadece **üst boşluğu** belirler. | `margin-top: 15px;` |
| `margin-right` | Sadece **sağ boşluğu** belirler. | `margin-right: 20px;` |
| `margin-bottom` | Sadece **alt boşluğu** belirler. | `margin-bottom: 15px;` |
| `margin-left` | Sadece **sol boşluğu** belirler. | `margin-left: 20px;` |

**Örnek Kullanım (Toplu):**
```css
.kutu {
  /* Padding (İç boşluk) */
  padding: 20px;           /* Üst, sağ, alt ve sol için aynı */
  padding: 10px 15px 20px 5px;  /* Üst, sağ, alt, sol farklı değerler */
  padding-top: 25px;       /* Sadece üst boşluk */
  padding-right: 15px;     /* Sadece sağ boşluk */
  padding-bottom: 20px;    /* Sadece alt boşluk */
  padding-left: 10px;      /* Sadece sol boşluk */

  /* Border (Kenarlık) */
  border-style: solid;          /* Çizgi tipi */
  border-top-style: dashed;     /* Üst kenar çizgi tipi */
  border-width: 2px;            /* Tüm kenarlar kalınlık */
  border-bottom-width: 4px;     /* Alt kenar kalınlık */
  border-color: #333333;        /* Tüm kenar rengi */
  border-left-color: red;       /* Sol kenar rengi */

  /* Margin (Dış boşluk) */
  margin: 20px;                 /* Tüm kenarlar aynı */
  margin: 10px 15px 20px 5px;   /* Üst, sağ, alt, sol farklı */
  margin-top: 25px;             /* Sadece üst boşluk */
  margin-right: 15px;           /* Sadece sağ boşluk */
  margin-bottom: 20px;          /* Sadece alt boşluk */
  margin-left: 10px;            /* Sadece sol boşluk */
}
```

---

### Box Sizing: `border-box`  

- Normalde CSS’de bir kutu modeli kullanıldığında:  
  - `width` ve `height` sadece **içerik (content)** alanını kapsar.  
  - `padding` ve `border` eklediğinizde kutunun toplam boyutu büyür.  

- `box-sizing: border-box;` kullanırsanız:  
  - `width` ve `height` **kutunun toplam boyutunu ifade eder**.  
  - Yani **padding ve border, bu toplam boyutun içine dahil edilir**.  
  - Böylece kutu dışa taşmaz, sadece içerik alanı küçülür.  

**Örnek Karşılaştırma:**  

```css
/* Normal (content-box) */
div {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
/* Toplam genişlik: 200(width) + 20(padding sol veya üst) + 20(sağ veya alt) + 5(border sol veya üst) + 5(border sağ veya alt) = 250px */

/* Border-box */
div {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
/* Toplam genişlik: 200px, padding ve border bu 200px’in içinde hesaplanır */
```

---

### `margin: auto;` 

- `margin: auto;` özellikle **blok (block) elementlerde** kullanıldığında, elementin yatayda otomatik olarak **ortalanmasını** sağlar.  
- Genellikle **width** değeri belirlenmiş containerlar için tercih edilir.  
- Dikeyde otomatik ortalama yapmaz, sadece yatay eksende etkilidir.  

**Örnek Kullanım :**

```css
div {
    width: 300px;
    margin: auto; /* Div yatayda ortalanır */
    border: 1px solid black;
    padding: 20px;
}
```

---

### Kutu Konumlandırma: `position`

- HTML elementlerinin sayfa üzerindeki konumunu ayarlamak için `position` özelliği kullanılır.  

**Position Değerleri:**

- `static` → Varsayılan konumlandırma. Normal akışta yer alır.  
- `relative` → Kutuyu normal konumuna göre **kaydırabilir**. Boşluk yine normal konumda bırakılır.  
- `fixed` → Kutuyu sayfa **üzerinde sabitler**. Sayfa kaydırılsa bile hareket etmez. Örn: sabit reklam veya üst barlar.  
- `absolute` → Kutuyu **en yakın konumlandırılmış üst (relative/absolute/fixed) container** içine göre sabitler.
- `sticky` → Normal akışta hareket eden ama scroll sırasında belirli bir noktaya gelince sayfaya göre sabitlenen bir konumlandırma türüdür.

<img width="640" height="212" alt="image" src="https://github.com/user-attachments/assets/37c1738c-fd9d-40a0-8e55-fe587e4871ab" />          <br>

**Konumlandırma:**

- `top: x;` → Elementin **üstten x kadar uzaklığını** belirler.  
- `bottom: x;` → Elementin **alttan x kadar uzaklığını** belirler.  
- `left: x;` → Elementin **soldan x kadar uzaklığını** belirler.  
- `right: x;` → Elementin **sağdan x kadar uzaklığını** belirler.  

> Bu değerler yalnızca `relative`, `absolute`, `fixed` veya `sticky` position ile çalışır.  
> `static` için top/left/right/bottom değerleri etkisizdir.

**Örnek Kullanım:**

```css
/* Relative */
div.relative {
  position: relative;
  top: 20px;   /* Normal konumdan 20px aşağı kaydır */
  left: 30px;  /* Normal konumdan 30px sağa kaydır */
}

/* Fixed */
div.fixed {
  position: fixed;
  top: 10px;   /* Sayfanın üstünden 10px */
  right: 10px; /* Sayfanın sağından 10px */
}

/* Absolute */
div.absolute {
  position: absolute;
  top: 50px; 
  left: 50px;
}
```

---

### Kutu Sıralaması: `z-index`

- `z-index` özelliği, **üst üste binen kutuların hangi sırada görüneceğini** belirler.  
- **Yüksek değer** → önde görünür.  
- **Düşük veya negatif değer** → arkada görünür.  
- `z-index` sadece **position: relative, absolute, fixed veya sticky** ile çalışan elementlerde geçerlidir.  

**Örnek Kullanım:**

```css
/* Önde görünmesi için */
div.öne {
  position: relative;
  z-index: 10;   /* Diğer kutuların üstünde görünür */
  width: 100px;
  height: 100px;
  background-color: orange;
}

/* Arkada görünmesi için */
div.arka {
  position: relative;
  z-index: -1;  /* Diğer kutuların arkasında görünür */
  width: 100px;
  height: 100px;
  background-color: lightblue;
}
```

>**NOT :**
>
> Eğer iki kutu aynı `z-index` değerine sahipse, HTML akış sırasına göre üstte olan kutu önde görünür.
> `z-index` değeri negatif, sıfır veya pozitif olabilir.

---

### Taşma Kontrolü: `overflow`

- `overflow` özelliği, bir kutu içeriği **taştığında nasıl davranacağını** belirler.
  
**Değerler ve Anlamları**

| Değer     | Açıklama |
|-----------|----------|
| `visible` | Varsayılan değerdir. Taşan içerik kutunun dışına taşar ve görünür. |
| `hidden`  | Taşan içerik **görünmez** olur, kullanıcı göremez. |
| `scroll`  | Taşma olmasa bile **her zaman kaydırma çubuğu** görünür. |
| `auto`    | Taşma olursa **kaydırma çubuğu** otomatik görünür, taşmazsa kaydırma çubuğu yoktur. |

**Örnek Kullanım:**

```css
div.kutu {
  width: 200px;
  height: 100px;
  border: 1px solid #333;
  overflow: auto; /* Taşarsa kaydırma çubuğu görünür */
}
```

---

### Kutuları Konumlandırma ve Görünürlük Kontrolü

- `float` → Bir kutuyu **istenilen yöne yaslamak** için kullanılır (sol veya sağ).  
- `visibility: hidden` → Kutuyu **görünmez yapar**, ancak kutunun yer kapladığı alan hâlâ durur.  
- `display: none` → Kutuyu **görünmez yapar ve alanını kaldırır**, yani sanki HTML’de yokmuş gibi davranır.  

**Örnek Kullanım:**

```css
/* Float ile sağa yaslama */
div.float-sag {
  float: right;
  width: 100px;
  height: 50px;
  background-color: lightblue;
}

/* Visibility ile görünmez yapma (alan durur) */
div.gorunmez-alan {
  visibility: hidden;
  width: 100px;
  height: 50px;
  background-color: pink;
}

/* Display ile tamamen kaldırma */
div.gorunmez-tamamen {
  display: none;
  width: 100px;
  height: 50px;
  background-color: orange;
}
```

---

### Kenar Yuvarlama: `border-radius`

- `border-radius` özelliği, bir kutunun **köşelerini yuvarlatmak** için kullanılır.  
  
**Örnek Kullanım:**

```css
/* Tüm köşeleri 10px yuvarlat */
div.kose-yuvarlak {
  width: 100px;
  height: 100px;
  background-color: lightgreen;
  border-radius: 10px;
}

/* Tüm köşeleri %50 ile tamamen yuvarlak yap (daire) */
div.daire {
  width: 100px;
  height: 100px;
  background-color: lightcoral;
  border-radius: 50%;
}

/* Sadece üst köşeleri yuvarlat */
div.ust-yuvarlak {
  width: 120px;
  height: 80px;
  background-color: lightblue;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}
```

---

### Kutu Gölgelendirme: `box-shadow`

- `box-shadow` özelliği, bir kutuya **gölge efekti** eklemek için kullanılır.  

**Parametreler:**

| Parametre | Açıklama |
|-----------|----------|
| `none`    | Varsayılan değer. Gölge yok. |
| `h-shadow` | Gölgenin **yatay uzaklığı** (pozitif → sağa, negatif → sola). |
| `v-shadow` | Gölgenin **dikey uzaklığı** (pozitif → aşağı, negatif → yukarı). |
| `blur`     | Gölgenin **kenarlarının yumuşaklığı**. Değer ne kadar büyükse, gölge o kadar **bulanık ve yayvan** olur; 0 px ise gölge **keskin hatlı**dır. |
| `spread`   | Gölgenin **boyutunu kutuya göre genişletme veya daraltma**. Pozitif değer gölgeyi kutunun her yönünde büyütür, negatif değer küçültür. |
| `color`   | Gölgenin rengi. |
| `inset`   | Gölgeyi **kutunun iç tarafına** uygular. |

- Kullanım formatı:  `box-shadow: h-shadow v-shadow blur spread color inset;`

**Örnek Kullanım:**

```css
/* Temel gölge */
div.golge {
  width: 150px;
  height: 100px;
  background-color: lightblue;
  box-shadow: 5px 5px 10px gray;
}

/* İç gölge */
div.ic-golge {
  width: 150px;
  height: 100px;
  background-color: lightgreen;
  box-shadow: inset 3px 3px 5px darkgreen;
}

/* Gölge + yayılma + renk */
div.golge-ozel {
  width: 150px;
  height: 100px;
  background-color: orange;
  box-shadow: 4px 4px 8px 2px rgba(0,0,0,0.5);
}
```

---

## Arka Plan Özellikleri (`background`)

CSS ile bir kutunun veya sayfanın arka planını **renk, resim ve konum ayarlarıyla** kontrol edebiliriz.      
Renk ve resim birlikte kullanıldığında, renk resmin altında görünür.

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `background-color` | Sadece arka plan rengini belirler. | `background-color: #ffcccc;` |
| `background-image` | Arka plana resim koyar. | `background-image: url('resim.jpg');` |

### - `background-repeat`

- `background-repeat` özelliği, **arka plan resminin kutu içinde tekrar edip etmeyeceğini** belirler.  
- Bu özellik sayesinde bir resmin yatayda, dikeyde veya her iki yönde tekrarlanmasını kontrol edebilirsiniz.

**Değerler:**

| Değer | Açıklama |
|-------|----------|
| `repeat` | Hem yatay hem dikey yönde resmi tekrarlar. (Varsayılan) |
| `no-repeat` | Resmi tekrarlamaz, sadece bir kez gösterir. |
| `repeat-x` | Sadece yatay eksende resmi tekrarlar. |
| `repeat-y` | Sadece dikey eksende resmi tekrarlar. |

**Örnek Kullanım:**
```css
div.tekrar {
  background-repeat: no-repeat;
}
```

### - `background-attachment`

- `background-attachment` özelliği, arka plan resminin **sayfa kaydırıldığında nasıl davranacağını** belirler.  
- Bu özellik sayesinde resmin, sayfa kaydırıldığında hareket edip etmeyeceğini kontrol edebilirsiniz.

**Değerler:**

| Değer   | Açıklama |
|---------|----------|
| `scroll` | Varsayılan değerdir. Sayfa kaydırıldığında arka plan resmi da kayar. |
| `fixed`  | Arka plan resmi **sayfaya sabitlenir**. Sayfa kaydırılsa bile resim hareket etmez. |

**Örnek Kullanım:**

```css
div.sabit {
  background-image: url('resim.jpg');  /* Arka plan resmi */
  background-attachment: fixed;        /* Resim sayfaya sabitlenir */
}

div.kaydir {
  background-image: url('resim.jpg');
  background-attachment: scroll;       /* Resim kaydırılır, varsayılan */
}
```

### `background-position`

- `background-position` özelliği, arka plan resminin **kutunun içinde nerede konumlanacağını** belirler.  
- Bu özellik sayesinde resmin yatay ve dikey konumunu kolayca ayarlayabilirsiniz.

**Örnek Değerler:**

| Değer           | Açıklama |
|-----------------|----------|
| `left top`      | Resim kutunun **sol üst köşesinde** başlar. |
| `center center` | Resim kutunun **tam ortasında** konumlanır. |
| `right bottom`  | Resim kutunun **sağ alt köşesinde** başlar. |
| `x y`           | Piksel veya yüzde ile **belirli bir konum** ayarlayabilirsiniz. Örn: `50px 20px`, `25% 50%`. |

**Örnek Kullanım:**

```css
div.konum {
  background-image: url('resim.jpg'); /* Arka plan resmi */
  background-position: center top;    /* Resim kutunun üst ortasında konumlanır */
}

div.konum2 {
  background-image: url('resim.jpg');
  background-position: 50px 20px;     /* 50px soldan, 20px üstten */
}
```

### `background-size`

- `background-size` özelliği, arka plan resminin **genişlik ve yükseklik** ayarlarını kontrol eder.  
- Bu sayede resmi kutuya sığdırabilir veya kutuyu tamamen kaplayacak şekilde ölçeklendirebilirsiniz.

**Örnek Değerler:**

| Değer      | Açıklama |
|------------|----------|
| `px`       | Resmin genişlik veya yüksekliğini **piksel cinsinden** belirler. Örn: `100px 200px` |
| `%`        | Resmin boyutunu kutu boyutuna göre **yüzde ile** belirler. Örn: `50% 100%` |
| `cover`    | Resim kutuyu tamamen **kaplayacak şekilde** ölçeklenir, taşabilir. |
| `contain`  | Resim kutuya **sığacak şekilde** ölçeklenir, taşmaz, kenarlarda boşluk olabilir. |

**Örnek Kullanım:**

```css
div.boyut {
  background-image: url('resim.jpg'); /* Arka plan resmi */
  background-size: cover;             /* Kutu tamamen kaplanır */
}

div.boyut2 {
  background-image: url('resim.jpg');
  background-size: contain;           /* Resim kutuya sığar, taşmaz */
}

div.boyut3 {
  background-image: url('resim.jpg');
  background-size: 200px 100px;       /* Piksel ile genişlik ve yükseklik ayarlanır */
}

div.boyut4 {
  background-image: url('resim.jpg');
  background-size: 50% 100%;          /* Yüzde ile genişlik ve yükseklik ayarlanır */
}
```

### `background` Özelliği

- `background` özelliği, **arka plan rengini, resmini, tekrar davranışını, konumunu ve boyutunu** tek bir satırda tanımlamak için kullanılır.  
- Böylece `background-color`, `background-image`, `background-repeat`, `background-position` ve `background-size` gibi ayrı özellikleri ayrı ayrı yazmak yerine **toplu ve kısa** bir şekilde tanımlayabilirsiniz.

**Kullanım Sırası:**

```text
background: <renk> <resim> <repeat> <attachment> <position> / <size>;
```

**Örnek Kullanım:**
```css
/* 1. Basit renk ve resim */
div.toplu1 {
  background: #f0f0f0 url('resim.jpg');
}

/* 2. Renk + resim + tekrar yok + sabit + konum + boyut */
div.toplu2 {
  background: #fff url('resim.jpg') no-repeat fixed center top / cover;
}

/* 3. Yalnızca resim ve konum + boyut */
div.toplu3 {
  background: url('resim.jpg') no-repeat center center / contain;
}
```

---

### `flex-direction`

- `flex-direction` özelliği, **Flex konteyner içindeki öğelerin dizilme yönünü** belirler.  
- Flex konteyner oluşturmak için önce `display: flex;` kullanılır.  

**Değerler:**

| Değer    | Açıklama |
|----------|----------|
| `row`    | Öğeler **yatay eksende** (soldan sağa) dizilir. Varsayılan değerdir. |
| `column` | Öğeler **dikey eksende** (üstten alta) dizilir. |

**Örnek Kullanım:**

```css
/* Yatay dizilim */
div.kutu-row {
  display: flex;         /* Flex konteyner oluşturur */
  flex-direction: row;   /* Öğeler yan yana dizilir */
}

/* Dikey dizilim */
div.kutu-column {
  display: flex;
  flex-direction: column; /* Öğeler alt alta dizilir */
}
```

---

### Flex Kutuların Sıralamasını Ters Çevirme (`flex-direction`)

- `flex-direction` özelliği, Flex konteyner içindeki öğelerin **dizilme yönünü ve sıralamasını** belirler.  
- Normal veya ters yönlerde yatay veya dikey olarak sıralama yapılabilir.

**Değerler ve Açıklamaları:**

| Değer               | Açıklama |
|--------------------|----------|
| `row`              | Yatay eksende **normal sıralama** (1 → 2 → 3). |
| `row-reverse`      | Yatay eksende **ters sıralama** (3 → 2 → 1). |
| `column`           | Dikey eksende **normal sıralama** (1 üste, 3 alta). |
| `column-reverse`   | Dikey eksende **ters sıralama** (3 üste, 1 alta). |

#### Örnek Kullanım:

```css
/* Normal yatay sıralama */
div.flex-row {
  display: flex;
  flex-direction: row; /* 1 → 2 → 3 */
}

/* Ters yatay sıralama */
div.flex-row-reverse {
  display: flex;
  flex-direction: row-reverse; /* 3 → 2 → 1 */
}

/* Normal dikey sıralama */
div.flex-column {
  display: flex;
  flex-direction: column; /* 1 üste, 3 alta */
}

/* Ters dikey sıralama */
div.flex-column-reverse {
  display: flex;
  flex-direction: column-reverse; /* 3 üste, 1 alta */
}
```

---

### Flex Kutularda Sütun Hizasında Hizalama

- Flex konteynerde, kutuların **dikey veya yatay hizalanması** için `align-items` ve `justify-content` özellikleri kullanılır.  
- `flex-direction` ile dizilim yönünü belirledikten sonra hizalama ayarlanabilir.

#### `align-items` Değerleri (Dikey veya Sol/Sağ Hizalama)

| Değer               | Açıklama |
|--------------------|----------|
| `flex-start`        | Elemanları **başlangıç noktasına hizalar** (sol veya üst). |
| `flex-end`          | Elemanları **bitiş noktasına hizalar** (sağ veya alt). |
| `center`            | Elemanları **orta noktaya hizalar** (dikey ortalama). |

> Not: `flex-direction: column;` kullanıldığında, elemanların **genişliği varsayılan olarak sınırlı** olur, hizalama bu duruma göre uygulanır.

#### `justify-content` Değerleri (Yatay veya Ana Eksende Ortalama)

| Değer               | Açıklama |
|--------------------|----------|
| `center`            | Ana eksende (row ise yatay) elemanları ortalar. |
| `flex-start`        | Ana eksende elemanları başlangıca hizalar. |
| `flex-end`          | Ana eksende elemanları sona hizalar. |
| `space-between`     | Elemanlar arasında eşit boşluk bırakır. |
| `space-around`      | Elemanların çevresinde eşit boşluk bırakır. |

>**NOT :**
>
> Bizim öncesinde (`flex-direction`) belirlediğimiz kurallara göre biri yatayda biri dikeyde ortalama yapar.

**Örnek Kullanım:**

```css
/* Dikeyde üst hizalama */
div.flex-sol {
  display: flex;
  align-items: flex-start; /* üst hizalama veya sol hizalama */
}

/* Dikeyde alt hizalama */
div.flex-sag {
  display: flex;
  align-items: flex-end; /* alt hizalama veya sağ hizalama */
}

/* Dikeyde ortalama */
div.flex-orta-dikey {
  display: flex;
  align-items: center;
}

/* Yatayda ortalama */
div.flex-orta-yatay {
  display: flex;
  justify-content: center; /* yatayda ortalar */
}

/* Dikeyde kolon yönünde elemanları ortalama */
div.flex-column-orta {
  display: flex;
  flex-direction: column;
  align-items: center;      /* genişliği sınırlı elemanlar ortalanır */
  justify-content: center;   /* dikeyde ortalar */
}
```

---

### Esnek Kutuların Genişlik Yüzdelerini Belirleme (`flex`)

- Flex konteynerde kutuların **oranlı genişliğini** belirlemek için `flex` özelliği kullanılır.
- Yani kutuların genişliğini birbirinden bağımsız şekilde belirlemeyi sağlar.
- `flex: x;` → Buradaki **x**, toplam flex değerleri içinde kutunun payını belirtir.  

**Örnek Senaryo:**

3 adet kutu var ve flex değerleri şöyle:  

| Kutu | Flex Değeri |
|------|------------|
| 1. kutu | 3 |
| 2. kutu | 1 |
| 3. kutu | 1 |

- Toplam flex değeri = 3 + 1 + 1 = 5  
- **Genişlik oranları:**  
  - 1. kutu → 3 / 5 = 60%  
  - 2. kutu → 1 / 5 = 20%  
  - 3. kutu → 1 / 5 = 20%  

**Örnek Kullanım:**

```css
div.konteyner {
  display: flex;
}

div.kutu1 {
  flex: 3; /* Toplamın 3/5'i genişliğinde */
}

div.kutu2 {
  flex: 1; /* Toplamın 1/5'i genişliğinde */
}

div.kutu3 {
  flex: 1; /* Toplamın 1/5'i genişliğinde */
}
```

---

## Dar Ekranlarda Flex Kutuları Alt Satırlara Kaydırma (Mobil)

- Mobil veya dar ekranlarda, yan yana dizilmiş kutular **kısıtlı alan yüzünden taşabilir** ve kullanıcı deneyimi olumsuz etkilenebilir.  
- Bu durumu önlemek ve kutuların **alt satıra geçmesini sağlamak** için `flex-wrap` özelliği kullanılır.  

### Temel Çözüm Adımları

1. **Flex wrap kullanımı:**
```css
.kapsayici {
  display: flex;
  flex-wrap: wrap; /* Kutular taşarsa alt satıra geçer */
}
```

2. **Genişlik Belirleme:**
- Her kutuya `width` veya `flex-basis` ile minimum genişlik verilir.

```css
.kutu {
  width: 250px; /* Dar ekranlarda taşmayı kontrol eder */
  // ya da
  flex-basis: 250px; /* Kutunun başlangıç genişliği */
}
```

> Farklar:
>
> `width` → Sabit genişlik verir, flex konteynerin oranları veya wrap durumuna göre değişmez.    
> `flex-basis` → Kutunun başlangıç genişliğini belirler ama flex konteynerin flex değerleri ile birlikte esneyebilir.

3. **Alt Satıra Geçiş:**
- Eğer toplam kutu genişliği kapsayıcı genişliğini aşarsa, fazla kutular otomatik olarak alt satıra kayar.

**Örnek Kullanım:**    
HTML Dosyası :    
```html
<div class="kapsayici">
  <div class="kutu">Kutu 1</div>
  <div class="kutu">Kutu 2</div>
  <div class="kutu">Kutu 3</div>
  <div class="kutu">Kutu 4</div>
</div>
```
  CSS Dosyası :
```css
.kapsayici {
  display: flex;
  flex-wrap: wrap; /* Dar ekranlarda alt satıra geçmesini sağlar */
}

.kutu {
  width: 250px; /* Her kutunun genişliği */
  margin: 10px;
  background-color: #f0f0f0;
}
```

---
### 📚 Konu Akışı

**⬅️ Önceki:** [**Metinlerin Biçimlendirilmesi**](03-metinlerin-biçimlendirmesi.md)   
**➡️ Sonraki:** [**Tablo ve Menü Tasarımı**](05-tablo-ve-menü-tasarımı.md)
