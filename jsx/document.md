# JSX ile İçerik Oluşturma

## Temel İçeriği Gösterme

1. **React ve ReactDOM Kütüphanelerini İçe Aktar:**

    ```jsx
    import React from 'react';
    import ReactDOM from 'react-dom/client';
    ```

    - React ve ReactDOM kütüphaneleri projeye eklenir. React, kullanıcı arayüzü oluşturmak için kullanılırken, ReactDOM, React uygulamasını HTML sayfasına yerleştirmek için kullanılır.
2. **HTML'de Hedef Elemanı Seç:**

    ```jsx
    const el = document.getElementById('root');
    ```

    - HTML'deki 'root' id'li bir eleman seçilir. Bu eleman, React uygulamasının render edileceği hedef div'i temsil eder.
3. **ReactDOM Root Oluştur:**

    ```jsx
    const root = ReactDOM.createRoot(el);
    ```

    - **`createRoot`** fonksiyonu, bir React uygulamasının kökünü oluşturur. Bu kök, render işlemlerini yönetir.
4. **React Uygulama Komponenti (App):**

    ```jsx
    function App() {
      return <h1>Hello Cosmos!</h1>;
    }
    ```

    - Basit bir **`App`** adında bir React fonksiyonel bileşeni tanımlanır. Bu bileşen, ekrana sadece "Hello Cosmos!" başlığını render eder.
5. **Uygulamayı Render Et:**

    ```jsx
    root.render(<App />);
    ```

    - **`root`** üzerinden **`render`** metodu çağrılarak, **`App`** bileşeni 'root' elemanına render edilir. Yani, "Hello Cosmos!" başlığı sayfada görüntülenir.

```jsx
// src -> index.js
import React from 'react';
import ReactDOM from 'react-dom/client';

const el = document.getElementById('root');

const root = ReactDOM.createRoot(el);

function App() {
  return <h1>Hello Cosmos!</h1>;
}

root.render(<App />);
```

## JSX İçinde JavaScript Değişkenlerini Yazdırma

1. **Fonksiyonel Bileşen Oluşturma:**

    ```jsx
    function App() {
    ```

    - **`App`** adında bir fonksiyonel bileşen (component) oluşturuluyor. React uygulamalarındaki arayüz elemanlarını temsil eden yapıdır.
2. **Mesaj Değişkeni Oluşturma:**

    ```jsx
    let message = 'Bye There!';
    ```

    - **`message`** adında bir değişken oluşturuluyor ve varsayılan değeri 'Bye There!' olarak atanıyor.
3. **Rastgele Mesaj Seçimi:**

    ```jsx
    if (Math.random() > 0.5) {
      message = 'Hello There!';
    }
    ```

    - **`Math.random()`** fonksiyonu, 0 ile 1 arasında rastgele bir sayı döndürür. Eğer bu sayı 0.5'ten büyükse, **`message`** değeri 'Hello There!' olarak güncellenir.
4. **JSX ile Mesajın Gösterimi:**

    ```jsx
    return <h1>{message}</h1>;
    ```

    - JSX (JavaScript XML) kullanarak, belirlenen **`message`** değeri **`<h1>`** başlığı içinde ekrana yazdırılır. Bu, değişkenin değerine bağlı olarak 'Hello There!' veya 'Bye There!' mesajını gösterecektir.

    ```jsx
    ...
    function App() {
      let message = 'Bye There!';
      if (Math.random() > 0.5) {
        message = 'Hello There!';
      }
      return <h1>{message}</h1>;
    }
    ...
    ```

## Kısa JS İfadeleri

1**. İlk Örnek:**

```jsx
function App() {
  const date = new Date();
  const time = date.toLocaleTimeString();

  return <h1>{time}</h1>;
}
```

- Bu örnekte, **`date`** adında bir değişken oluşturuluyor ve anlık tarih ve saat bilgisi alınıyor. Daha sonra **`toLocaleTimeString()`** fonksiyonu kullanılarak bu tarih-saat bilgisi yerel saat dilimine göre biçimlendiriliyor. Sonuç olarak, bu biçimlendirilmiş zaman değeri JSX içinde bir başlık etiketi ile gösteriliyor.

**2. İkinci Örnek:**

```jsx
function App() {
  return <h1>{new Date().toLocaleTimeString()}</h1>;
}
```

- İkinci örnekte ise doğrudan tek satırda, değişken tanımlamadan tarih-saat bilgisi alınıp, **`toLocaleTimeString()`** fonksiyonu kullanılarak yerel saat dilimine göre biçimlendirilmiş zaman değeri JSX içinde gösteriliyor.

**Farklar ve İpuçları:**

- İlk örnekte, tarih ve saat bilgisini daha önce tanımlanan bir değişken içinde saklayıp, ardından bu değişkeni kullanarak JSX içinde gösteriyoruz. Bu, kodun daha okunabilir olmasını sağlar, çünkü zaman bilgisi değişken içinde adlandırılmıştır.
- İkinci örnekte ise, tarih ve saat bilgisi doğrudan JSX içinde tek bir satırda oluşturulup kullanılıyor. Bu özellikle kısa süreli ve tek kullanımlık bir değişken için pratik olabilir.

## Kod Alıştırması: JSX İle Hızlı Pratik

Aşağıdaki App bileşeni üzerinde çalışmalar yapılması gerekiyor. Adınızı göstermesi gerekiyor. Hadi düzeltelim!

1. Adınızı boş dizeye 4. satırda ekleyin.
2. **`name`** değişkenini h1 elementinde yazdırın.

```jsx
...
function App() {
 const name = '';

 return (
  <div>
   My name is:
   <h1></h1>
  </div>
 );
}
...
```

### Egzersiz Çözümü

```jsx
...
function App() {
 const name = 'Bilbo Baggins';

 return (
  <div>
   My name is:
   <h1>{name}</h1>
  </div>
 );
}
...
```

## Tipik Bileşen Düzenleri

```jsx
...
function App() {
  const name = 'Anıl';
  const age = 26;
  return (
    <h1>
      My name is {name} and I am {age} years old.
    </h1>
  );
}

```

**Açıklama:**

1. **Değişken Tanımlama:** **`const name = 'Anıl';`** ve **`const age = 26;`** satırları, **`name`** ve **`age`** adında iki değişken tanımlar. Bu değişkenler, isim ve yaş bilgilerini içerir.
2. **JSX Kullanımı:** JSX (JavaScript XML), JavaScript içinde HTML benzeri bir sözdizimi sağlar. **`<h1>`** etiketi içindeki **`My name is {name} and I am {age} years old.`** ifadesi, değişkenleri kullanarak bir metin içeriği oluşturur.

## Props İle Öğeleri Özelleştirme

```jsx
...
function App() {
  const inputType = 'number';
  const minValue = 5;
  return <input type={inputType} min={minValue} max={10} style={{ border: '3px solid #ddd' }} />;
}
...
```

**Açıklama:**

1. **Değişken Tanımlama:** **`const inputType = 'number';`** ve **`const minValue = 5;`** satırları, **`inputType`** ve **`minValue`** adında iki değişken tanımlar. **`inputType`**, bir sayı alacak olan input'un tipini belirtirken, **`minValue`** ise input'un minimum değerini belirtir.
2. **JSX ile Input Oluşturma:** **`<input type={inputType} min={minValue} max={10} style={{ border: '3px solid #ddd' }} />`** satırı, bir input elementini JSX ile oluşturur. Bu input, **`number`** tipinde olup, minimum değeri **`minValue`** ve maksimum değeri **`10`** olarak belirlenmiştir.
3. **Stil Verme:** **`style={{ border: '3px solid #ddd' }}`** satırı, input elemanına CSS benzeri stil özellikleri uygular. Bu örnekte, input'un çerçevesine gri bir kenarlık ekler.

## HTML'i JSX'e Dönüştürme

```jsx
...
function App() {
  // JSX içinde prop isimleri camelCase olarak yazılmalıdır.
  return <textarea autoFocus={true} />;
}
...
```

**Açıklama:**

1. **Textarea Oluşturma:** **`<textarea autoFocus={true} />`** ifadesi, React bileşenlerinden biri olan **`textarea`** elemanını oluşturur. Bu eleman, bir metin giriş alanıdır.
2. **AutoFocus Özelliği:** **`autoFocus={true}`** özelliği, **`textarea`** elemanının otomatik olarak odaklanmasını sağlar. Yani, sayfa yüklendiğinde bu metin giriş alanı otomatik olarak seçilmiş olur.
3. **Prop İsimlendirme:** React'te prop isimleri camelCase olarak yazılmalıdır. Örneğin, **`autoFocus`** yerine **`auto-focus`** gibi kelimeler arasında tire (**``**) kullanılmaz; bunun yerine her yeni kelime büyük harfle başlar. Bu örnek, React'te props kullanırken isimlendirme kuralını göstermektedir.

## JSX İçinde Stil Uygulama

```jsx
...
function App() {
  // Burada, maxLength={10} ile input'a en fazla 10 karakter girebileceğimizi belirtiyoruz.
  return <input maxLength={10} />;
}
...
```

**Açıklama:**

1. **Input Oluşturma:** **`<input maxLength={10} />`** ifadesi, React bileşenlerinden biri olan **`input`** elemanını oluşturur. Bu eleman, kullanıcının metin girebileceği bir alanı temsil eder.
2. **maxLength Özelliği:** **`maxLength={10}`** özelliği, kullanıcının bu input alanına girebileceği maksimum karakter sayısını belirtir. Bu örnekte, en fazla 10 karakter girebileceğimizi ifade eder.
3. **Sayıları JSX'de Gösterme:** JSX içinde sayıları artık string şeklinde belirtmek yerine süslü parantez içinde gösteriyoruz. Örneğin, **`{10}`** şeklinde kullanılan bu ifade, JSX içinde bir sayıyı temsil eder.

```jsx
...
function App() {
  // className özelliği, elemana bir veya birden fazla CSS sınıfı atamamıza olanak tanır.
  return <input className="inputArea" />;
}
...
```

**Açıklama:**

1. **className Özelliği:** **`className="inputArea"`** özelliği, bu input elemanına bir veya birden fazla CSS sınıfı atamamıza olanak tanır. Bu örnekte, "inputArea" sınıfını kullanıyoruz.
2. **JSX'de class İsimleri:** JSX içinde class isimleri artık "className" olarak gösterilir. HTML'de **`class`** olarak kullanılan ifade, JSX içinde **`className`** olarak yazılmalıdır. Bu, JSX'in JavaScript'e daha yakın olmasını sağlar.

```jsx
...
function App() {
  // Style özelliklerini belirlemek için JSX içinde bir obje kullanıyoruz.
  // Her stil özelliği, obje içinde bir key-value çifti olarak belirtilir.
  // JSX içinde stil özellikleri camelCase şeklinde yazılır (paddingTop şeklinde, padding-top değil).
  return <input style={{ padding: '5px', marginTop: '15px' }} />;
}
...
```

**Açıklama:**

1. **Stil Özellikleri:** Stil özelliklerini belirlemek için JSX içinde bir obje kullanıyoruz. Bu obje içindeki her key-value çifti, bir stil özelliğini temsil eder. Örneğin, **`padding: '5px'`** ifadesi, bu input elemanına 5 piksellik bir iç kenarlık ekler.
2. **JSX'de Stil Özellikleri:** JSX içinde stil özellikleri belirlenirken, CSS'ten farklı olarak camelCase kullanılır. Yani, **`padding-top`** yerine **`paddingTop`** şeklinde yazılır.

## Kod Alıştırması: JSX Dönüşümüyle Pratik Yapma

JSX Dönüşümünü Uygula
HTML'i JSX'e çevirirken beş kuralı hatırla.

1. Tüm prop isimleri camelCase büyük-küçük harf kullanımına uyar.
2. Sayı öznitelikleri süslü parantez içinde kullanılır.
3. 'true' olan boolean'lar sadece özelliğin adıyla yazılabilir.
4. 'class' özniteliği 'className' olarak yazılır.
5. Inline Style obje olarak sağlanır.

```jsx
import React from 'react';

function App() {
  return (
    <div class="wrapper">
      <textarea readonly="true" maxlength="3" spellcheck="true" 
     style="background-color: gray;"
      />
    </div>
  );   
}

export default App;
```

### Egzersiz Çözümü

```jsx
import React from 'react';

function App() {
  return (
    <div className="wrapper">
      <textarea readOnly maxLength={3} spellCheck 
     style={{backgroundColor: 'gray'}}
      />
    </div>
  );   
}

export default App;
```

## Bileşenleri Ayıklama

İlk olarak, **`index.js`** dosyasına bakalım:

```jsx
// index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const el = document.getElementById('root');
const root = ReactDOM.createRoot(el);

root.render(<App />);
```

1. **`import App from './App';`**: Bu satır, **`App`** adlı bileşeni './App' dosyasından içe aktarır. Bu bileşen, uygulamanın temel bileşeni olabilir.
2. **`const el = document.getElementById('root');`**: HTML belgesindeki 'root' id'sine sahip bir elementi seçer ve bu elementi **`el`** değişkenine atar.
3. **`const root = ReactDOM.createRoot(el);`**: **`createRoot`** metodunu kullanarak bir root oluşturur. React 18 ve sonrasında, **`createRoot`** kullanılarak asenkron rendering ve concurrent mod özellikleri kullanılabilir.
4. **`root.render(<App />);`**: Oluşturduğumuz root üzerine **`App`** bileşenini render eder. Yani, **`App`** bileşeni, **`root`** üzerindeki 'root' elementine eklenir ve görüntülenir.

Şimdi de **`App.js`** dosyasına bakalım:

```jsx
// App.js

function App() {
  return <h1>App Js</h1>;
}

export default App;
```

1. **`function App() { ... }`**: Bu satırda, **`App`** adlı basit bir React fonksiyon bileşeni tanımlanıyor. Bu bileşen, bir JSX döndürerek bir kullanıcı arayüzü oluşturur..
2. **`export default App;`**: **`App`** bileşenini dışa aktarır. Bu, diğer dosyalardan **`App`** bileşenini içe aktarabilmemizi sağlar.

Özetle, **`index.js`** dosyası, React uygulamasının başlangıcını yapar ve **`App.js`** dosyasındaki **`App`** bileşenini kullanarak bir şeyler görüntüler. React, bu şekilde modüler ve bileşen odaklı bir yapı sunarak, büyük uygulamaların daha yönetilebilir olmasına olanak tanır.

## Modül Sistemleri Genel Bakış

1. **Modül**: Bir JavaScript dosyasındaki bir veya birden fazla fonksiyon, değişken veya sınıfı içeren bir birimdir. Bu dosya, başka dosyalar tarafından içe aktarılabilir (import) veya dışa aktarılabilir (export) öğeler içerebilir.
2. **İçe Aktarma (Import) ve Dışa Aktarma (Export)**: Modül sistemleri, bir dosyadan diğerine veri veya kod transferini sağlar. Bir dosyadan başka bir dosyaya bir şey göndermek için **`export`** kullanılır ve bu şeyi almak için de **`import`** kullanılır.

### **Örnek:**

1. **Person.js (Dışa Aktarma):**

```jsx

// Person.js

class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Merhaba, ben ${this.name}!`);
  }
}

// Person sınıfını dışa aktarıyoruz
export default Person;
```

**App.js (İçe Aktarma):**

```jsx
// App.js

// Person.js dosyasındaki Person sınıfını içe aktarıyoruz
import Person from './Person';

// Bir örnek oluşturuyoruz
const person1 = new Person('Ahmet', 25);

// Örneğin metodunu çağırıyoruz
person1.sayHello();
```

Bu örnekte, **`Person.js`** dosyasında **`Person`** adlı bir sınıfı dışa aktardık (**`export default`**). Ardından, **`App.js`** dosyasında bu sınıfı içe aktardık (**`import Person from './Person';`**) ve bir örnek oluşturarak metodunu çağırdık.

### **İç İçe Dosyalar ve Yollar:**

1. **Dosya Yolları (File Paths):** React projelerinde, dosyalar arasındaki ilişkileri ifade etmek için genellikle "dosya yolları" kullanılır. Örneğin, **`./`** ile başlayan bir dosya yolu, mevcut çalışma dizininden itibaren bir dosya veya dizine referans verir. Ayrıca, **`../`** kullanarak bir üst dizine referans verebilirsiniz.
2. **İç İçe Modüller (Nested Modules):** Projeler genellikle birbiri içine geçmiş modüller içerir. Örneğin, bir "components" klasörü içinde başka bir "Header" klasörü olabilir. İç içe modüller, dosya yollarını doğru bir şekilde kullanarak birbirine referans verebilir.

### **Birden Fazla Fonksiyon veya Değişkeni İçe Aktarma ve Dışa Aktarma:**

1. **Birden Fazla İçe Aktarma (Named Imports):** Bir dosyadan birden fazla fonksiyon veya değişken içe aktarmak için, bu öğeleri dosyada isimlendirmeniz ve sonra bu isimleri kullanarak içe aktarmanız gerekir.

    Örneğin:

    ```jsx
    // utils.js
    
    export const add = (a, b) => a + b;
    export const subtract = (a, b) => a - b;
    ```

    ```jsx
    // App.js
    
    import { add, subtract } from './utils';
    
    console.log(add(5, 3)); // 8
    console.log(subtract(5, 3)); // 2
    ```

2. **Her Şeyi İçe Aktarma (Import Everything as an Alias):** Tüm modülü bir nesne olarak içe aktarabilirsiniz.

    Örneğin:

    ```jsx
    // utils.js
    
    export const add = (a, b) => a + b;
    export const subtract = (a, b) => a - b;
    ```

    ```jsx
    // App.js
    
    import * as utils from './utils';
    
    console.log(utils.add(5, 3)); // 8
    console.log(utils.subtract(5, 3)); // 2
    ```

Bu özellikler, React projelerindeki dosyalar arası etkileşimi yönetmek ve kodu düzenlemek için oldukça güçlü araçlar sağlar. İyi bir proje yapısı oluşturmak ve dosya düzenini anlamak, büyük ölçekli projelerde daha fazla esneklik ve bakım kolaylığı sağlar.
