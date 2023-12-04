# Yeniden Kullanılabilir Bileşenlerle Oluşum

## Yeniden Kullanılabilir Bileşenler Nedir?

"Reusable Components" (Yeniden Kullanılabilir Bileşenler), yazılım geliştirmenin temel prensiplerinden biridir ve React gibi bileşen tabanlı kütüphanelerde önemli bir kavramdır. İsterseniz bu terimi biraz daha detaylı bir şekilde inceleyelim:

1. **Tanım:**
    - Reusable Components, genellikle bir yazılım uygulamasının farklı kısımlarında birden çok kez kullanılabilen, bağımsız, modüler ve yeniden kullanılabilir parçalardır.
2. **Avantajları:**
    - **Daha Az Kod, Daha Az Hata:** Bileşenleri tekrar kullanmak, kodunuzun daha kısa olmasını sağlar ve bu da hataların azalmasına yardımcı olabilir.
    - **Bakım Kolaylığı:** Değişiklikler veya güncellemeler, bir bileşeni güncellediğinizde tüm uygulamaya otomatik olarak yansır. Bu, bakımı kolaylaştırır.
    - **Daha İyi Tasarım:** Bileşenler, kodunuzu mantıklı parçalara böler, bu da daha iyi bir tasarım ve organizasyon sağlar.
3. **React ve Reusable Components:**
    - React, bileşen tabanlı bir kütüphanedir ve bu nedenle bileşenleri oluşturmak ve kullanmak üzerine kuruludur.
    - React bileşenleri, başka bileşenlerin içinde veya yan yana yerleştirilebilir.
    - Örneğin, bir "Button" bileşeni oluşturup bu bileşeni farklı sayfalarda veya farklı bileşenlerde kullanabilirsiniz.
4. **Örnek:**
    - Aşağıda, yeniden kullanılabilir bir "Button" bileşeni örneği bulunmaktadır:

    ```jsx
    // Button.js
    
    import React from 'react';
    
    function Button({ label, onClick }) {
      return (
        <button onClick={onClick}>
          {label}
        </button>
      );
    }
    
    export default Button;
    ```

    Bu bileşeni şu şekilde kullanabilirsiniz:

    ```jsx
    // App.js
    
    import React from 'react';
    import Button from './Button';
    
    function App() {
      const handleClick = () => {
        console.log('Button Clicked!');
      };
    
      return (
        <div>
          <h1>React Reusable Components</h1>
          <Button label="Click Me" onClick={handleClick} />
        </div>
      );
    }
    
    export default App;
    ```

    Bu örnekte, **`Button`** bileşeni "App" bileşeninde kullanılmış ve bu sayede "Button" bileşenini farklı yerlerde tekrar kullanabilirsiniz.

## Temel Bileşenler Oluşturma

### ProfileCard.js

1. **Fonksiyonu Anlamak:** İlk olarak, **`ProfileCard`** adlı bir fonksiyon tanımlanmış. Bu fonksiyon, bir profil kartını temsil edecek.
2. **JSX:** **`<div>Profile Card</div>`** JSX ifadesi, tarayıcıda görüntülenecek olan "Profile Card" metnini içeren bir **`<div>`** elementini temsil eder.
3. **Dışa Aktarma (Export):** Fonksiyon, **`export default`** ile dışa aktarılıyor. Bu, başka dosyalardan bu bileşeni içe aktarabilmemizi sağlar.

Bu bileşenin kullanımı şu şekilde olabilir:

```jsx
// ProfileCard.js

function ProfileCard() {
  return <div>Profile Card</div>;
}

export default ProfileCard;
```

Yukarıdaki örnekte, **`ProfileCard`** bileşeni **`App`** bileşeni içinde kullanılarak sayfada "Profile Card" metnini içeren bir bölüm oluşturulmuş olur.

### App.js

1. **Import İşlemi:**
    - **`ProfileCard`** bileşenini kullanabilmek için öncelikle dosyadan içeri alıyoruz (**`import ProfileCard from './ProfileCard';`**). Bu sayede **`ProfileCard`** bileşenini bu dosyada kullanabiliriz.
2. **Ana Bileşen (App):**
    - **`App`** adında bir ana bileşen tanımlıyoruz. Bu bileşen, sayfamızın genel yapısını temsil eder.
3. **JSX İle İçerik Oluşturma:**
    - **`return`** ifadesi içinde JSX kullanarak sayfa içeriğimizi oluşturuyoruz. JSX, JavaScript ile HTML'i bir araya getiren bir sözdizimidir.
    - **`<div>`** elemanları, HTML benzeri yapılar oluşturmak için kullanılır. Örneğin, sayfa üzerinde "Personal Digital Assistants" metnini içeren bir **`<div>`** elemanı oluşturuyoruz.
4. **Bileşen Kullanımı:**
    - **`<ProfileCard />`** ifadesi, **`ProfileCard`** bileşenini çağırmak ve sayfa içinde kullanmak için kullanılır. Bu bileşeni üç kez tekrarlıyoruz, bu da sayfada üç adet profil kartı oluşturulmasını sağlar.
5. **Export İşlemi:**
    - Son olarak, **`export default App;`** ifadesi ile **`App`** bileşenini dışa aktarıyoruz. Bu, bu bileşeni başka dosyalardan içe aktarabilmemizi sağlar.

```jsx
// App.js

import ProfileCard from './ProfileCard';

function App() {
  return (
    <div>
      <div>Personal Digital Assistants</div>

      <ProfileCard />
      <ProfileCard />
      <ProfileCard />
    </div>
  );
}

export default App;
```

### index.js

1. **React ve ReactDOM Kütüphanelerini İçe Aktar:**

    ```jsx
    // index.js
    
    import React from 'react';
    import ReactDOM from 'react-dom/client';
    ```

    - **`React`** ve **`ReactDOM`** kütüphaneleri, React uygulamalarını oluşturmak ve yönetmek için kullanılır.
2. **HTML'de Hedef Elemanı Seç:**

    ```jsx
    const el = document.getElementById('root');
    ```

    - **`document.getElementById('root')`** ifadesi, HTML'deki bir elemanı seçer. Bu, React uygulamasının render edileceği hedef elemanı temsil eder.
3. **ReactDOM Root Oluştur:**

    ```jsx
    const root = ReactDOM.createRoot(el);
    ```

    - **`createRoot`** fonksiyonu, bir React uygulamasının kökünü oluşturur. Bu, React uygulamasının render işlemlerini yönetir.
4. **React Uygulama Komponenti (App):**

    ```jsx
    const el = document.getElementById('root');
    
    const root = ReactDOM.createRoot(el);
    
    function App() {
      return <h1>Hello React Learner!</h1>;
    }
    ```

    - **`App`** adında bir React fonksiyonel bileşeni tanımlanır. Bu bileşen, ekrana "Hello React Learner!" başlığını render eder.
5. **Uygulamayı Render Et:**

    ```jsx
    root.render(<App />);
    ```

    - **`root.render(<App />)`** ifadesi, oluşturulan **`root`** üzerinden **`App`** bileşenini hedef elemana render eder. Yani, "Hello React Learner!" başlığı sayfada görüntülenir.

## Props Eklemek

### App.js

1. **Ana Bileşen (App) Oluştur:**

    ```jsx
    function App() {
      return (
        <div>
          <div>Personal Digital Assistants</div>
    
          <ProfileCard title="Alexa" handle="@alexa99" />
          <ProfileCard title="Cortana" handle="@cortana32" />
          <ProfileCard title="Siri" handle="@siri01" />
        </div>
      );
    }
    ```

    - **`App`** adında bir React fonksiyonel bileşeni oluşturulur. Bu bileşen, sayfanın ana yapısını temsil eder. İçinde **`ProfileCard`** bileşenini kullanarak kişisel dijital asistanları gösterir.
2. **Profil Kartlarını Kullan:**

    ```jsx
    <ProfileCard title="Alexa" handle="@alexa99" />
    <ProfileCard title="Cortana" handle="@cortana32" />
    <ProfileCard title="Siri" handle="@siri01" />
    ```

    - **`ProfileCard`** bileşenini üç kez kullanarak, her bir dijital asistan için bir profil kartı oluşturulur. Her bir kart, farklı bir başlık (**`title`**) ve kullanıcı adı (**`handle`**) ile özelleştirilir.

İpuçları ve Trickler:

- Props kullanarak bileşenlere dinamik veriler iletebilirsin. **`title`** ve **`handle`** gibi özellikler, **`ProfileCard`** bileşenine geçirilen props'lar aracılığıyla dinamik olarak değiştirilebilir.
- JSX içinde süslü parantezler **`{}`** kullanarak JavaScript ifadelerini entegre edebilirsin. Örneğin, **`title="Alexa"`** gibi sabit değerler yerine dinamik veriler kullanabilirsin.

### ProfileCard.js

1. **Bileşeni Tanımla ve Props Kullan:**

    ```jsx
    jsxCopy code
    function ProfileCard(props) {
      return (
        <div>
          <div>Title is {props.title}</div>
          <div>Handle is {props.handle}</div>
        </div>
      );
    }
    
    ```

    - **`ProfileCard`** adında bir React fonksiyonel bileşen tanımlanır. Bu bileşen, **`props`** adlı bir parametre alır. **`props`** parametresi, bileşene dışarıdan geçirilen verileri içerir. Bu örnekte, **`title`** ve **`handle`** adlı props'ları kullanarak bileşen içinde dinamik içerik oluşturulur.
2. **Props Kullanarak Dinamik İçerik Oluştur:**

    ```jsx
    jsxCopy code
    <div>
      <div>Title is {props.title}</div><div>Handle is {props.handle}</div>
    </div>
    
    ```

    - JSX içinde süslü parantez **`{}`** kullanarak, props içindeki verilere erişilir ve bu verileri kullanarak dinamik içerik oluşturulur. Örneğin, **`Title is {props.title}`** ifadesi, "Title is" metni ile **`title`** prop'ındaki değeri birleştirir.

İpuçları ve Trickler:

- **`props`** adı genellikle bileşenlere dışarıdan veri geçmek için kullanılır, ancak başka bir isim de kullanabilirsin. Önemli olan, bileşen içinde bu parametreyi kullanarak dışarıdan gelen verilere erişmektir.
- JSX içinde süslü parantezleri kullanarak, JavaScript ifadelerini içeriye entegre edebilir ve dinamik içerik oluşturabilirsin. Bu, bileşenlerini daha esnek hale getirir ve farklı verilerle kullanmanı sağlar.

## Argüman Yapısını Parçalama

1. **Destructuring ile Props Al:**

    ```jsx
    function ProfileCard({ title, handle }) { // === const { title, handle } = props; // === const title = props.title && const handle = props.handle
      return (
        <div>
          <div>Title is {title}</div>
          <div>Handle is {handle}</div>
        </div>
      );
    }
    ```

    - Fonksiyon parametreleri içinde direkt olarak **`props`** objesini destructuring ile açarak, **`title`** ve **`handle`** gibi özelliklere direkt olarak erişebilirsin. Bu, kodun daha kısa ve okunabilir olmasını sağlar.
    - `function ProfileCard({ title, handle })` & `const { title, handle } = props;` & `const title = props.title && const handle = props.handle` hepsi aynı tanımlamayı gerçekleştirmektedir.

## Kod Alıştırması: Props ile Pratik Yapma

Proje, iki bileşeni içeriyor: **`App`** ve **`BrightText`**.

- **`App`** bileşeni, üç **`BrightText`** örneğini gösterir.
- **`BrightText`** bileşeni, bir prop olan **`color`**'u bekliyor, ancak şu anda **`App`**, üç **`BrightText`** örneğine bu prop'u sağlamıyor.

**Hedef: `App` bileşenindeki üç `BrightText` öğesine birer `color` prop'u eklemek.**

1. **İlk renk "red" olmalı.**
2. **İkinci renk "green" olmalı.**
3. **Üçüncü renk "blue" olmalı.**

**`BrightText`** bileşeni zaten tamamlanmış durumda - ona herhangi bir değişiklik yapmanız gerekmiyor.

### App.js

```jsx
import React from 'react';
import BrightText from './BrightText';
function App() {
 return (
  <div>
   <BrightText />
   <BrightText />
   <BrightText />
  </div>
 );
}
export default App;
```

### BrightText.js

```jsx
import React from 'react';
export default function BrightText({ color }) {
  const style = { color: color };
  return <h1 style={style}>Hi!</h1>
}
```

### Egzersiz Çözümü

### App.js

```jsx
import React from 'react';
import BrightText from './BrightText'
function App() {
    return (
        <div>
          <BrightText color="red"/>
          <BrightText color="green"/>
          <BrightText color="blue"/>
        </div>
    );
}
export default App;
```

## Görselleri Dahil Etme

Bu React uygulamasında, **`App`** bileşeni, üç farklı **`ProfileCard`** bileşenini içeriyor. Her bir **`ProfileCard`**, farklı dijital asistanları temsil ediyor.

Birkaç küçük detay ve trick:

1. **Dosya İçe Aktarma:**
    - **`import`** ifadeleri, farklı bileşenleri ve görüntüleri (**`ProfileCard`**, **`AlexaImage`**, vb.) dosyadan içe aktarıyor. **`import`** kullanımı, dışarıdan farklı bileşenleri veya kaynakları (resimler, metinler) kodunuza eklemenizi sağlar.
2. **Resim İçe Aktarma:**
    - **`AlexaImage`**, **`CortanaImage`**, ve **`SiriImage`** gibi resimleri de içeri aktarıyoruz. Bu resimler ilgili dijital asistanların logolarını temsil ediyor.

    ```jsx
    import ProfileCard from './ProfileCard';
    import AlexaImage from './images/alexa.png';
    import CortanaImage from './images/cortana.png';
    import SiriImage from './images/siri.png';
    
    function App() {
     ...
    }
    
    export default App;
    ```

3. **Statik Resimler:**
    - Statik resimler, genellikle projenin içinde bulunan ve değişmeyen resim dosyalarını temsil eder. Bu resimler, proje dosyalarına dahil edildiğinden, onlara referans vermek için genellikle resim dosyalarının yolu kullanılır.
    - Base64, bir resmi bir dize olarak kodlayan bir yöntemdir. Bu, resmi dosyaya dışa bağımlı olmadan, kod içinde doğrudan gömebileceğiniz anlamına gelir. Bu, HTTP istekleri yapmadan ve kullanıcının tarayıcısında ayrı bir dosya indirmesine gerek kalmadan resimleri hızlı bir şekilde göstermenizi sağlar.
4. **Dinamik Resimler:**
    - Dinamik resimler genellikle dış kaynaklardan veya kullanıcının etkileşimi sonucu alınan resimlerdir. Bu durumda, resimler genellikle base64 formatında bir dize olarak alınır ve dinamik olarak gösterilir. Bu, özellikle kullanıcının tarayıcısında ayrı bir resim dosyası indirmek yerine, bir API'den veya başka bir kaynaktan alınan resimleri hızlı bir şekilde göstermek için kullanışlıdır.

Küçük ipuçları:

- **Base64 Avantajları:**
  - Base64, küçük resim dosyalarını içeri almak için harika bir seçenektir, ancak büyük resim dosyalarını base64'e çevirmek, kodunuzun boyutunu artırabilir. Bu nedenle, genellikle küçük resim dosyaları veya ikonlar için tercih edilir.
- **Dinamik Resimlerde Async İşlemler:**
  - Dinamik resimleri asenkron olarak alıyorsanız, resmin base64 formatında bir dizeye dönüşmesi bir asenkron işlem olabilir. Bu durumda, resmin yüklenmesini beklemek için uygun işlemleri gerçekleştirmelisiniz.

## Görüntü Erişilebilirliğini Yönetme

### App.js

1. **Ana Bileşen:**

    ```jsx
    function App() {
      return (
        <div>
         <div>Personal Digital Assistants</div>
         <ProfileCard title="Alexa" handle="@alexa99" image={AlexaImage} />
         <ProfileCard title="Cortana" handle="@cortana32" image={CortanaImage} />
         <ProfileCard title="Siri" handle="@siri01" image={SiriImage} />
        </div>
      );
    }
    ```

    - **`App`** adlı ana bileşen, profilleri temsil eden üç **`ProfileCard`** bileşenini içerir. Her biri farklı bir dijital asistanı temsil eder.

### ProfileCard.js

1. **ProfileCard Bileşeni:**

    ```jsx
    function ProfileCard({ title, handle, image }) {
      return (
        <div>
          <img src={image} alt={title} />
          <div>Title is {title}</div>
          <div>Handle is {handle}</div>
        </div>
      );
    }
    ```

    - **`ProfileCard`** bileşeni, bir profil kartını temsil eder. **`title`**, **`handle`** ve **`image`** adlı prop'ları alır ve bu bilgileri kullanarak bir kartı render eder.
    - **`img`** etiketi, **`image`** prop'undan gelen resmi gösterir.

<aside>
💡 **UYARI:** Eğer img elementine “alt” attribute eklemezsek ‘Terminal’ sayfasında bir uyarı ile karşılaşacağız.

</aside>

### Terminal

1. “**img elements must have an alt prop, either with meaningful text, or an empty string for decorative images jsx-a11y/alt-text”**

Bu uyarı, JSX (JavaScript XML) kodunuzda bir **`<img>`** elementinin kullanıldığı ve bu elementin bir **`alt`** özelliğine sahip olmaması durumunda görünen bir uyarıdır. Bu uyarı, erişilebilirlik standartlarına uygunluğu sağlamak amacıyla ekran okuyucular gibi araçlar tarafından kullanılan yardımcı teknolojilere destek vermek için gelir.

Uyarı şu iki durumu içerir:

1. **Anlamlı Metin:** **`<img>`** elementinin **`alt`** özelliği, görüntünün içeriğini açıklayan anlamlı bir metin içermelidir. Bu, görüntü yüklenemediğinde veya görüntüye erişim sağlanamadığında kullanıcıya bir açıklama sağlar.

    ```jsx
    jsxCopy code
    <img src="path/to/image.jpg" alt="Güzel bir manzara" />
    
    ```

2. **Boş Dize (Decorative Images):** Eğer görüntü sadece dekoratif bir öğe ise ve sayfanın anlamını veya içeriğini etkilemiyorsa, **`alt`** özelliği boş bir dize (**`""`**) olarak ayarlanabilir.

    ```jsx
    jsxCopy code
    <img src="path/to/decorative-image.jpg" alt="" />
    
    ```

Bu uyarı, web uygulamanızın erişilebilirliğini artırmak ve kullanıcı deneyimini geliştirmek için önemlidir. Eğer görseller önemli bilgiler içeriyorsa veya sayfanın içeriğini anlamak için önemliyse, **`alt`** özelliği doğru bir şekilde ayarlanmalıdır.

## NPM ile CSS Kütüphaneleri Eklemek

1. `npm install bulma` : Bulma adlı bir CSS framework'ünü projenize eklemek için kullanılan bir komuttur. Bulma, modern ve kullanımı kolay bir CSS framework'üdür. Sayfa düzeni, bileşenler, formlar ve diğer UI unsurları için hazır CSS sınıflarını içerir.

    Bu komut, npm (Node Package Manager) aracılığıyla Bulma'nın projenize indirilmesini ve kullanılmasını sağlar. Projenizin bağımlılıklarına Bulma'yı ekler ve böylece Bulma'nın sunduğu stil ve bileşenleri projenizde kullanabilirsiniz.

    Komutu çalıştırdıktan sonra, projenizin kök dizininde Bulma'nın dosyaları ve klasörleri (**`node_modules`** altında) yer alacak ve bu dosyaları projenizde kullanabilirsiniz. Bu şekilde, Bulma tarafından sağlanan CSS sınıflarını ve bileşenleri HTML dosyalarınızda kullanarak, kolayca özelleştirilmiş ve şık bir kullanıcı arayüzü oluşturabilirsiniz.

2. **Bulma İçe Aktarma:**

    ```jsx
    import 'bulma/css/bulma.css';
    ```

    - Kodun en üstünde, Bulma CSS framework'ünün tarayıcıda kullanılabilmesi için Bulma stil dosyasını içe aktarıyoruz.
3. **Bulma Stillerini Kullanma:**
    - Bulma'nın sağladığı stil kuralları, uygulama içindeki diğer bileşenlerin görünümünü düzenlemek için kullanılabilir. Bu stil kuralları, **`bulma.css`** dosyasının içinde tanımlanmıştır.

Küçük Trick'ler:

- **Hızlı Stil Uygulama:**
  - Bu, özellikle stil konusunda daha fazla bilgiye sahip olmayanlar için hızlı bir stil uygulama yöntemidir. Bulma gibi CSS framework'leri, şık ve hazır stil kuralları sağlayarak geliştirme sürecini hızlandırabilir.
- **Modüler Geliştirme:**
  - Uygulama stilini başka bileşenlerle birleştirmek ve modüler bir şekilde geliştirmek için CSS framework'leri kullanılabilir. Bu, stilin daha iyi yönetilmesine ve uygulamanın daha düzenli olmasına yardımcı olabilir.

## HTML'nin Büyük Bir Yığını

### ProfileCard.js

1. **Bulma CSS Stilleri:**
    - **`className`** özelliği ile Bulma CSS framework'ünün stillerini kullanarak, kartın ve içeriklerinin görünümünü düzenler. Örneğin, **`card`**, **`card-image`**, **`image`**, **`title`**, **`subtitle`** gibi Bulma sınıfları kullanılarak belirli stil kuralları uygulanır.
2. **Bileşen İçeriği:**
    - Bileşenin içeriği, Bulma sınıfları kullanılarak kartın iç yapısını oluşturur. **`card`**, **`card-image`**, **`image`**, **`card-content`**, **`media-content`**, **`title`**, **`subtitle`** gibi sınıflar, görünümü düzenlemek için kullanılır.

    ```jsx
    function ProfileCard({ title, handle, image }) {
      return (
        <div className="card">
          <div className="card-image">
            <figure className="image is-1by1">
              <img src={image} alt={title} />
            </figure>
          </div>
          <div className="card-content">
            <div className="media-content">
              <p className="title is-4">{title}</p>
              <p className="subtitle is-6">{handle}</p>
            </div>
          </div>
        </div>
      );
    }
    
    export default ProfileCard;
    ```

Küçük Trick'ler:

- **Dinamik İçerik:**
  - Bileşen, **`title`**, **`handle`**, ve **`image`** prop'larından gelen verilere dayalı olarak dinamik içerik oluşturur. Bu, aynı bileşeni farklı verilerle kullanabilme esnekliği sağlar.

### App.js

1. **Bulma CSS Framework:**

    ```jsx
    import 'bulma/css/bulma.css';
    ```

    - Uygulama, Bulma CSS framework'ünün stil kurallarını kullanarak görünümünü oluşturur. **`bulma.css`** dosyası, Bulma stil kurallarını içerir ve bu kurallar uygulama genelinde kullanılır.
2. **Başlık ve Yapı:**

    ```jsx
    <h1 className="title is-1 has-text-centered">Personal Digital Assistants</h1>
    <div className="container">
      <section className="section">
        <div className="columns">
          {/* ... */}
        </div>
      </section>
    </div>
    ```

    - Uygulamanın başlığı ve temel yapısı Bulma stil kuralları kullanılarak düzenlenir. **`title`**, **`container`**, **`section`**, ve **`columns`** gibi Bulma sınıfları, belirli stil özelliklerini uygular.

Küçük Trick'ler:

- **Grid Yapısı:**
  - **`columns`** ve **`column`** sınıfları kullanılarak sayfa, Bulma'nın grid yapısı üzerinde düzenlenir. Bu, sayfayı sütunlara böler ve içerikleri hizalar.
- **Başlık Stili:**
  - Başlık, Bulma'nın **`title`** ve **`has-text-centered`** sınıfları kullanılarak merkezi hizalanır ve belirli bir başlık stili alır.

## Stilin Son Dokunuşu

Bu React uygulaması, Bulma CSS framework'ü kullanılarak tasarlanmış ve üç farklı dijital asistanı temsil eden profil kartlarını içermektedir. İşte bu kod parçasını anlatan küçük bir açıklama:

### App.js

1. **Hero Bileşeni:**

    ```jsx
    <section className="hero is-primary">
      <div className="hero-body">
        <h1 className="title is-1 has-text-centered">Personal Digital Assistants</h1>
      </div>
    </section>
    ```

    - Bu, sayfanın başlık bölümünü oluşturan bir Bulma hero bileşenidir. **`is-primary`** sınıfı, başlığın renk temasını belirler.
2. **Profil Kartları ve Açıklamalar:**

    ```jsx
    <ProfileCard title="Alexa" handle="@alexa99" image={AlexaImage} description="Alexa was created by Amazon and helps you buy things" />
    {/* Benzer şekilde Cortana ve Siri için */}
    ```

    - Her profil kartı, başlık (**`title`**), kullanıcı adı (**`handle`**), bir resim (**`image`**) ve bir açıklama (**`description`**) alır. Bu, her bir dijital asistanın kısa bir açıklamasını içeren kartlar oluşturur.
3. **Açıklamalar ve Dinamik İçerik:**
    - Her profil kartı, farklı açıklamalarla özelleştirilebilir. Bu, uygulamanın dinamik içerik gösterme yeteneğini ve bileşenlere çeşitli verileri (props) iletebilme kabiliyetini gösterir.
4. **Responsive Tasarım:**
    - Bulma'nın **`columns`** ve **`column`** sınıfları, sayfayı sütunlara böler ve içeriği responsive bir şekilde düzenler. Bu, uygulamanın farklı ekran boyutlarına uyum sağlamasını sağlar.

Küçük Trick'ler:

- **Hero Bileşeni Kullanımı:**
  - **`hero`** ve **`hero-body`** sınıfları kullanılarak başlık bölümü belirgin hale getirilir. **`is-primary`** sınıfı ise başlık bölümünün rengini belirler.
- **Açıklama Ekleme:**
  - Profil kartlarına açıklama eklenerek, her dijital asistanın kısa bir tanımı sağlanır. Bu, kullanıcıya daha fazla bilgi sunar.
- **Bulma Grid Yapısı:**
  - **`columns`** ve **`column`** sınıfları, sayfayı sütunlara böler. Bu, sayfanın responsive tasarımını iyileştirir ve farklı ekran boyutlarına uyum sağlar.

### ProfileCard.js

Bu React bileşeni, bir dijital asistanın profil kartını temsil eden basit ve özelleştirilebilir bir kart yapısını içerir. İşte kodun anlatımı ve bazı küçük trick'ler:

1. **Card Bileşeni ve Resim Eklemek:**

    ```jsx
    <div className="card">
      <div className="card-image">
        <figure className="image is-1by1">
          <img src={image} alt={title} />
        </figure>
      </div>
    </div>
    ```

    - Kartın temel yapısı, **`card`** sınıfı altında bir resim içeren bir **`card-image`** içerir. **`image`** sınıfı ile resmin oranı belirlenir.
2. **Başlık ve Altbaşlık Eklemek:**

    ```jsx
    <div className="card-content">
      <div className="media-content">
        <p className="title is-4">{title}</p>
        <p className="subtitle is-6">{handle}</p>
      </div>
    </div>
    ```

    - **`card-content`** sınıfı, kartın içeriğini oluşturur. **`media-content`** içinde başlık (**`title`**) ve altbaşlık (**`handle`**) bulunur. **`title`** ve **`subtitle`** sınıfları, metnin stilini belirler.
3. **Açıklama Eklemek:**

    ```jsx
    <div className="content">{description}</div>
    ```

    - **`content`** sınıfı, kartın alt kısmında yer alır ve açıklamayı içerir. Bu, kartın daha fazla bilgi sunmasını sağlar.
4. **Props Kullanımı:**
    - **`{ title, handle, image, description }`** şeklinde destructuring kullanarak, bileşene dışarıdan bu özellikleri geçirebiliriz. Bu, bileşenin farklı verilerle tekrar kullanılabilir olmasını sağlar.
5. **Responsive Tasarım:**
    - Bulma'nın **`is-1by1`**, **`is-4`**, ve **`is-6`** gibi sınıfları, resim ve metin öğelerinin boyutunu ve düzenini belirler. Bu, kartın responsive bir şekilde görüntülenmesine yardımcı olur.

Küçük Trick'ler:

- **Media Content Kullanımı:**
  - **`media-content`** sınıfı, başlık ve altbaşlığı içerir. Bu, metin öğelerini düzenli bir şekilde gösterir.
- **Destructuring Props:**
  - **`{ title, handle, image, description }`** kullanarak, bileşene props'ları doğrudan çözerek kodu daha okunabilir ve sade hale getirir.
- **Responsive Tasarım Sınıfları:**
  - Bulma'nın responsive tasarım sınıfları, öğelerin farklı ekran boyutlarına uyum sağlamasını sağlar.
