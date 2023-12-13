# State: Uygulamanızı Nasıl Değiştirirsiniz?

## Başlangıç Uygulama Kurulumu

1. Proje dosyalarımızı oluşturuyoruz:

### index.js

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const el = document.getElementById('root');
const root = ReactDOM.createRoot(el);

root.render(<App />);
```

### App.js

```jsx
function App() {
  return <div>Show Animal List Here!</div>;
}

export default App;
```

### AnimalShow.js

```jsx
function AnimalShow() {
  return <div>Cow!</div>;
}

export default AnimalShow;
```

## Etkinlik Sistemi Tanıtımı

1. **Fonksiyonel Bileşen Oluşturmak:**

    ```jsx
    function App() {
    ```

    - **`function App()`** ifadesi, bir fonksiyonel React bileşeni oluşturur. Bu bileşen, uygulamanın temel bileşenidir.
2. **Click Olayını İzlemek ve Konsola Yazdırmak:**

    ```jsx
    const handleClick = () => {
      console.log('click');
    };
    ```

    - **`handleClick`** adında bir ok fonksiyonu tanımlanır. Bu fonksiyon, butona tıklandığında çalışır ve konsola 'click' yazısını yazar.
3. **Buton Eklemek ve Click Olayını Bağlamak:**

    ```jsx
    <button onClick={handleClick}>Add Animal</button>
    ```

    - **`<button>`** öğesi, kullanıcı tarafından tıklanabilir bir buton oluşturur. **`onClick`** prop'u, butona tıklandığında çağrılacak fonksiyonu belirler. Bu örnekte, **`handleClick`** fonksiyonu bağlanmıştır.
4. **Fonksiyonu Arrow Function İle Tanımlamak:**
    - **`const handleClick = () => { ... }`** ifadesi, bir arrow function (ok fonksiyonu) tanımlar. Arrow function'lar, fonksiyonu kısa ve net bir şekilde tanımlamak için kullanılır.
5. **Export İşlemi:**

    ```jsx
    export default App;
    ```

    - **`export default App;`** ifadesi, **`App`** fonksiyonunu diğer dosyalarda kullanılabilir hale getirir. Böylece bu bileşeni başka dosyalarda içe aktarabilirsiniz.

Küçük Trick'ler:

- **Arrow Function Kullanımı:**
  - **`const handleClick = () => { ... }`** ile fonksiyonu arrow function olarak tanımlamak, kısa ve anlaşılır bir şekilde işlemi gerçekleştirmenizi sağlar.
- **onClick Prop Kullanımı:**
  - **`onClick={handleClick}`** ile butona tıklandığında çağrılacak fonksiyonu belirlemek, etkileşimli işlemleri uygulamanın temelini oluşturur.
- **Console.log Kullanımı:**
  - **`console.log('click');`** ifadesi, tarayıcı konsoluna bir mesaj yazdırarak basit debug işlemleri yapmanıza olanak tanır.

## Kodlama Alıştırması: **Etkinliklerle Egzersiz**

- **Hedef:** Düğme öğesine bir tıklama olayı işleyicisi ekleyin.
- Düğmeye her tıklandığında `console.log`'a "Merhaba!" şeklinde bir mesaj yazdığınızdan emin olun.

```jsx
import React from 'react';

function App() {
    return (
        <div>
            <button>Click Me!</button>          
        </div>
    );
}

export default App;
```

### Egzersiz Çözümü

```jsx
import React from 'react';

function App() {
    const handleClick = () => {
        console.log('Hello there!')
    }
    return (
        <div>
            <button onClick={handleClick}>Click Me!</button>          
        </div>
    );
}

export default App;
```

## Durum Sistemi Tanıtımı

1. **State Kullanımı:**

    ```jsx
    import { useState } from 'react';
    ```

    - **`useState`** fonksiyonu, React uygulamalarında state yönetimini sağlar. Bu örnekte, **`count`** adında bir state ve bu state'i güncellemek için **`setCount`** fonksiyonu kullanılır.
2. **State İlk Değerini Belirleme:**

    ```jsx
    const [count, setCount] = useState(0);
    ```

    - **`useState(0)`** ifadesi, **`count`** adındaki state'in başlangıç değerini 0 olarak belirler. Ayrıca, bu state'i güncellemek için kullanılacak **`setCount`** fonksiyonunu tanımlar.
3. **Click Olayını İzlemek ve State'i Güncelleme:**

    ```jsx
    const handleClick = () => {
      setCount(count + 1);
    };
    ```

    - **`handleClick`** fonksiyonu, butona tıklandığında çağrılır ve **`setCount`** aracılığıyla **`count`** state'i bir artırılır.
4. **State'i JSX İçinde Kullanma:**

    ```jsx
    <div>Number of animals: {count}</div>
    ```

    - JSX içinde **`{count}`** ifadesi, **`count`** state'inin güncel değerini ekranda gösterir.
5. **useState Kullanımı ile State Tanımlama:**
    - **`const [count, setCount] = useState(0);`** ifadesi ile state tanımlama, React hook'larından olan **`useState`** hook'unu kullanarak state yönetimini gerçekleştirir.
6. **State Güncelleme Fonksiyonu İle Güncelleme:**
    - **`setCount(count + 1);`** ifadesi ile **`setCount`** fonksiyonu aracılığıyla **`count`** state'i güncellenir. Bu, React'te state'in güncellenmesi için yaygın bir yöntemdir.

Küçük Trick'ler:

- **State Kullanımının Temel Mantığı:**
  - **`useState`** hook'u, React uygulamalarında state yönetimini sağlar. State, uygulamanın dinamik ve etkileşimli olmasını sağlar.
- **State Güncelleme Fonksiyonu:**
  - State güncellemeleri, mevcut state değeri ve yeni değer arasında bir işlem yaparak gerçekleştirilir. Bu örnekte, **`setCount(count + 1);`** ile bir artırma işlemi yapılır.
- **JSX İçinde Değişken Kullanımı:**
  - JSX içinde **`{count}`** ifadesi, JavaScript ifadelerini içe almanızı ve dinamik olarak değerleri ekrana yazdırmanızı sağlar.

## Rastgele Bir Öğe Seçme

1. **`import` ifadesi**: Kod, **`useState`** adlı bir fonksiyonu React kütüphanesinden içe aktarıyor. **`useState`** fonksiyonu, bir bileşenin yerel durumunu (state) yönetmek için kullanılır.
2. **`getRandomAnimal` fonksiyonu**: Bu fonksiyon, önceden tanımlanmış bir hayvan listesinden rastgele bir hayvan ismi döndürür. **`Math.random()`** fonksiyonu rastgele bir sayı üretir ve bu sayı **`Math.floor()`** ile en yakın alt tam sayıya yuvarlanarak, bir dizi indeksi olarak kullanılır.
3. **`App` fonksiyon bileşeni**: Bu, uygulamanın ana bileşenidir (**`component`**). React, kullanıcı arayüzlerini bileşenlerden oluşturur. Bu bileşen, uygulamanın görünümünü ve davranışını tanımlar.
4. **Durum (State) Kullanımı**: **`useState`** kullanılarak **`animals`** adında bir durum değişkeni ve bu değişkeni güncellemek için bir **`setAnimals`** fonksiyonu oluşturulmuştur. Başlangıçta **`animals`** boş bir dizi olarak tanımlanmıştır.
5. **`handleClick` fonksiyonu**: Bu fonksiyon, kullanıcı butona tıkladığında tetiklenir. Fonksiyon, mevcut **`animals`** dizisine **`getRandomAnimal`** fonksiyonu ile elde edilen yeni bir hayvan ekler. **`setAnimals`** fonksiyonu, bu yeni diziyi **`animals`** durumuna atar, bu da bileşenin yeniden render edilmesine (çizilmesine) sebep olur.
6. **JSX Dönüş**: **`App`** bileşeni, JSX (JavaScript XML) formatında HTML benzeri bir yapı döndürür. Bu yapı, bir buton ve **`animals`** dizisini gösteren bir **`div`** içerir. Buton, **`handleClick`** fonksiyonuna bağlıdır.
7. **`export default App;`**: Bu ifade, **`App`** bileşenini dışa aktarır, böylece başka dosyalarda kullanılabilir.

```jsx
import { useState } from 'react';
function getRandomAnimal() {
  const animals = ['bird', 'cat', 'cow', 'dog', 'gator', 'horse'];
  return animals[Math.floor(Math.random() * animals.length)];
}
function App() {
  const [animals, setAnimals] = useState([]);
  const handleClick = () => {
    setAnimals([...animals, getRandomAnimal()]);
  };
  return (
    <div>
      <button onClick={handleClick}>Add Animal</button>
      <div>{animals}</div>
    </div>
  );
}
export default App;
```

**Önemli React Konsepti:**

- **Deklaratif Yaklaşım**: React, deklaratif bir yaklaşım kullanır. Yani, uygulamanın herhangi bir andaki durumu, bileşenlerin durumları ve özellikleri (props) ile tanımlanır. Bu durum veya özellikler değiştiğinde, React otomatik olarak arayüzü günceller.

## React'te Liste Oluşturma

### **`App.js` Dosyası**

Bu dosya uygulamanın ana bileşenini (**`App`**) içerir.

1. **İçe Aktarmalar (Imports)**: **`useState`** React'ten ve **`AnimalShow`** ise yerel bir dosyadan içe aktarılır. **`AnimalShow`** başka bir bileşendir ve bu bileşen bu dosyada kullanılacaktır.
2. **`getRandomAnimal` Fonksiyonu**: Rastgele bir hayvan ismi döndüren yardımcı fonksiyondur. Daha önce açıkladığım gibi çalışır.
3. **Durum (State) ve Olay İşleyici (Event Handler)**: **`useState`** kullanılarak **`animals`** adında bir durum değişkeni tanımlanır ve **`setAnimals`** bu durumu güncellemek için kullanılır. **`handleClick`** fonksiyonu, bu durumu güncelleyerek yeni hayvanlar ekler.
4. **`renderedAnimals` Değişkeni**: Bu, **`animals`** dizisinin her elemanı için **`AnimalShow`** bileşenini çağırarak bir dizi JSX elementi oluşturur. Her **`AnimalShow`** bileşenine **`type`** prop'u olarak hayvan ismi ve **`key`** prop'u olarak benzersiz bir anahtar (bu örnekte dizi indeksi) verilir.
5. **JSX Dönüşü**: **`App`** bileşeni, bir buton ve **`renderedAnimals`** dizisini gösteren bir yapı döndürür. Buton **`handleClick`** fonksiyonuna bağlıdır ve her tıklamada yeni bir hayvan ekler.

```jsx
import { useState } from 'react';
import AnimalShow from './AnimalShow';
function getRandomAnimal() {
  const animals = ['bird', 'cat', 'cow', 'dog', 'gator', 'horse'];
  return animals[Math.floor(Math.random() * animals.length)];
}
function App() {
  const [animals, setAnimals] = useState([]);
  const handleClick = () => {
    setAnimals([...animals, getRandomAnimal()]);
  };
  const renderedAnimals = animals.map((animal, idx) => {
    return <AnimalShow type={animal} key={idx} />;
  });
  return (
    <div>
      <button onClick={handleClick}>Add Animal</button>
      <div>{renderedAnimals}</div>
    </div>
  );
}
export default App;
```

### **`AnimalShow.js` Dosyası**

Bu dosya, **`AnimalShow`** adında başka bir bileşen içerir.

1. **Fonksiyon Bileşeni**: **`AnimalShow`** bir fonksiyon bileşenidir. Props olarak **`type`** alır. Bu prop, **`App.js`** dosyasında **`AnimalShow`** bileşenine verilen **`type`** prop'udur.
2. **JSX Dönüşü**: Bu bileşen, aldığı **`type`** prop'unu bir **`div`** içinde gösterir. Yani, **`type`** içindeki hayvan ismini ekranda görüntüler.

```jsx
function AnimalShow({ type }) {
  return <div>{type}</div>;
}
export default AnimalShow;
```

### **İlişki ve İletişim**

- **`App.js`** dosyasında, **`AnimalShow`** bileşeni, **`renderedAnimals`** içinde **`map`** fonksiyonu ile birden fazla kez çağrılır. Her çağrıda, **`type`** prop'u olarak bir hayvan ismi geçilir.
- **`AnimalShow`** bu prop'u alır ve ekranda gösterir. Böylece, **`App`** bileşeni içinde oluşturulan veri (**`animals`** listesi), başka bir bileşen olan **`AnimalShow`** tarafından kullanılır ve gösterilir.

## SVG'leri Yükleme ve Gösterme

Kodun başında, çeşitli hayvanlara ait SVG dosyaları içe aktarılır. Bu SVG dosyaları, **`./svg/`** dizininde yer alıyor ve her bir hayvan için ayrı bir dosya var. React, Webpack gibi modül paketleyicileri kullanarak statik dosyaları (görseller, SVG dosyaları vb.) içe aktarmanıza olanak tanır.

```jsx
import bird from './svg/bird.svg';
import cat from './svg/cat.svg';
// diğer hayvanlar için benzer içe aktarmalar
```

### **`svgMap` Objesi**

Bu obje, hayvan isimlerini anahtar olarak ve ilgili SVG dosyalarını değer olarak içerir. Bu yapı, hayvan isimlerine göre kolayca ilgili SVG'yi bulmamızı sağlar.

```jsx
const svgMap = { bird, cat, cow, dog, gator, horse };
```

### **`AnimalShow` Bileşeni**

**`AnimalShow`** bir fonksiyon bileşenidir ve **`type`** adında bir prop alır. Bu **`type`**, hangi hayvanın gösterileceğini belirtir.

```jsx
function AnimalShow({ type }) {
  return (
    <div>
      <img alt="animal" src={svgMap[type]} />
    </div>
  );
}
```

### Görselin Gösterilmesi

- Bileşen, **`type`** prop'una göre **`svgMap`** objesinden uygun SVG dosyasını seçer ve bir **`img`** etiketi içinde gösterir.
- **`src={svgMap[type]}`** ifadesi, **`type`** değerine göre doğru SVG dosyasının yolunu belirler.
- **`alt="animal"`** ifadesi, görüntünün alternatif metnini tanımlar. Bu, erişilebilirlik için önemlidir ve görüntü yüklenemezse veya görüntü okuyucuları tarafından kullanıldığında görüntülenir.

## Görüntü Boyutunu Artırma

1. **Import Statements**: **`import`** ifadeleri, kullanmak istediğiniz başka dosyalardaki değişkenleri veya modülleri yüklemenizi sağlar. Örneğin, **`import bird from './svg/bird.svg';`** satırı, aynı klasördeki **`svg`** klasöründen **`bird.svg`** dosyasını yükler.
2. **Functional Component**: Bu kodda **`AnimalShow`** adlı bir fonksiyonel komponent tanımlanmış. React, bu tür komponentleri kullanarak UI'ın nasıl görüneceğini tanımlar.
3. **Props**: **`AnimalShow`** komponenti, **`type`** adında bir prop (property) alır. Props, komponentlere veri aktarmak için kullanılır. Burada **`type`**, hangi hayvanın gösterileceğini belirler.
4. **useState Hook**: **`useState`** bir React Hook'u olup, komponent içinde durum (state) yönetimine olanak tanır. **`const [clicks, setClicks] = useState(0);`** satırı, **`clicks`** adında bir durum değişkeni ve bu değişkeni güncellemek için bir fonksiyon (**`setClicks`**) oluşturur.
5. **Event Handling**: **`handleClick`** fonksiyonu, kullanıcı tıklamasını yakalar ve **`clicks`** durumunu günceller.
6. **Rendering**: Komponent, JSX (JavaScript XML) kullanarak UI'ı render eder. Burada iki **`<img>`** etiketi kullanılmış: biri hayvan için, diğeri kalp için. Kalp resminin boyutu, **`clicks`** durumuna bağlı olarak değişir.

    ```jsx
    import { useState } from 'react';
    import bird from './svg/bird.svg';
    ...
    
    const svgMap = { bird, cat, cow, dog, gator, horse };
    
    function AnimalShow({ type }) {
      const [clicks, setClicks] = useState(0);
      const handleClick = () => {
        setClicks(clicks + 1);
      };
      return (
        <div onClick={handleClick}>
          <img alt="animal" src={svgMap[type]} />
          <img alt="heart" src={heart} style={{ width: 10 + 10 * clicks + 'px' }} />
        </div>
      );
    }
    
    export default AnimalShow;
    ```

### **İpuçları ve Püf Noktaları:**

- **Destructuring**: Props ve state değişkenlerini kullanırken, JavaScript'in destructuring özelliğini kullanabilirsiniz. Bu, kodunuzu daha temiz ve okunabilir yapar.
- **Conditional Rendering**: Eğer farklı hayvan türleri için farklı UI öğeleri göstermek isterseniz, JSX içinde koşullu ifadeler kullanabilirsiniz.
- **Performance Optimization**: Eğer performansla ilgili endişeleriniz varsa, **`React.memo`** veya **`useMemo`** gibi teknikleri kullanarak gereksiz renderları önleyebilirsiniz.
- **Styling**: Inline CSS stil kullanımı yerine, CSS modülleri veya styled-components gibi kütüphaneleri tercih edin. Bu, stil yönetimini daha modüler ve sürdürülebilir kılar.

## Özel CSS Ekleme

1. **Component Structure**: **`App`** ana komponenti ve **`AnimalShow`** alt komponenti var. **`App`**, uygulamanın ana giriş noktasıdır ve diğer komponentleri içerir.
2. **Importing Styles and Components**: **`import './App.css';`** ve **`import './AnimalShow.css';`** ile CSS dosyaları yükleniyor. Bu, komponentlerinize özgü stilleri tanımlamanızı sağlar. **`import AnimalShow from './AnimalShow';`** ifadesi ise **`AnimalShow`** komponentini yükler.
3. **State Management in Parent Component**: **`App`** komponentinde, **`useState`** kullanılarak uygulamanın durumu yönetiliyor. Bu, kullanıcı eylemlerine yanıt olarak UI'ın nasıl değişeceğini kontrol etmenizi sağlar. Örneğin, bir hayvan ekleme butonu (**`Add Animal`**) olabilir ve bu butona her basıldığında yeni bir **`AnimalShow`** komponenti oluşturulabilir.
4. **Event Handling**: **`onClick`** özelliği ile bir butona tıklama olayı ele alınıyor. Bu, kullanıcı etkileşimlerini yakalamanın temel bir yoludur.
5. **Rendering Child Components**: **`App`** içinde, **`AnimalShow`** komponentleri dinamik olarak render edilebilir. Bu, genellikle bir dizi veya liste üzerinde **`.map()`** gibi JavaScript fonksiyonları kullanılarak yapılır.

### App.js

    ```jsx
    import './App.css';
    import { useState } from 'react';
    import AnimalShow from './AnimalShow';
    
    ...
    
    function App() {
    ...
    
    ...
      return (
        <div className="app">
          <button onClick={handleClick}>Add Animal</button>
          <div>{renderedAnimals}</div>
        </div>
      );
    }
    ...
    ```

### AnimalShow.js

    ```jsx
    import './AnimalShow.css';
    import { useState } from 'react';
    ...
    
    const svgMap = { bird, cat, cow, dog, gator, horse };
    
    function AnimalShow({ type }) {
    ...
      );
    }
    
    export default AnimalShow;
    ```

### **İpuçları ve Püf Noktaları:**

- **Component Separation**: Her komponentin kendi işlevine odaklanması önemlidir. Bu, kodun okunabilirliğini ve bakımını kolaylaştırır.
- **Props Passing**: Alt komponentlere veri aktarımı için props kullanın. Bu, komponentler arasında veri akışını sağlar.
- **Reusable Components**: Komponentleri yeniden kullanılabilir yapın. Örneğin, **`AnimalShow`** birçok farklı hayvan türü için kullanılabilir.
- **CSS Modules or Styled Components**: Stil çakışmalarını önlemek için CSS Modülleri veya styled-components gibi yaklaşımları kullanmayı düşünün.
- **State Lifting**: Bazen, birden fazla alt komponentin aynı veriyi kullanması gerekebilir. Bu durumda, durumu üst komponente taşımak (state lifting) iyi bir çözüm olabilir.
