# Building with Reusable Components

## What is the Reusable Components?

"Reusable Components"  is one of the fundamental principles of software development and is an important concept in component-based libraries like React. Let's explore this term in a bit more detail:

1. **Definition:**
    - Reusable Components are independent, modular, and reusable parts that can be used multiple times in different parts of a software application.
2. **Advantages:**
    - **Less Code, Fewer Errors:** Reusing components makes your code shorter, which can lead to fewer errors.
    - **Ease of Maintenance:** Changes or updates automatically propagate throughout the entire application when you update a component, making maintenance easier.
    - **Better Design:** Components divide your code into logical parts, providing better design and organization.
3. **React and Reusable Components:**
    - React is a component-based library, built around creating and using components.
    - React components can be nested within other components or placed side by side.
    - For example, you can create a "Button" component and use it on different pages or within different components.
4. **Example:**
    - Below is an example of a reusable "Button" component:

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

    You can use this component as follows:

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

    In this example, the Button component has been used in the "App" component, allowing you to reuse the "Button" component in different places.

## Creating Core Components

### ProfileCard.js

1. **Understanding the Function:** Firstly, a function named **`ProfileCard`** is defined. This function represents a profile card.
2. **JSX:** The JSX expression **`<div>Profile Card</div>`** represents a **`<div>`** element containing the text "Profile Card," which will be displayed in the browser.
3. **Exporting:** The function is exported using **`export default`**. This allows us to import this component into other files.

The usage of this component could be as follows:

```jsx
// ProfileCard.js

function ProfileCard() {
  return <div>Profile Card</div>;
}

export default ProfileCard;
```

In the example above, the ProfileCard component is used within the App component, creating a section on the page containing the text 'Profile Card.

### App.js

1. **Import Process:**
    - To use the **`ProfileCard`** component, we first import it from the file (**`import ProfileCard from './ProfileCard';`**). This allows us to use the **`ProfileCard`** component in this file.
2. **Main Component (App):**
    - We define a main component named **`App`**, representing the overall structure of our page.
3. **Creating Content with JSX:**
    - Using JSX within the **`return`** statement, we create the content of our page. JSX is a syntax that combines JavaScript with HTML.
    - **`<div>`** elements are used to create HTML-like structures. For example, we create a **`<div>`** element containing the text "Personal Digital Assistants" on the page.
4. **Component Usage:**
    - The **`<ProfileCard />`** expression is used to call and use the **`ProfileCard`** component on the page. We repeat this component three times, resulting in the creation of three profile cards on the page.
5. **Export Process:**
    - Finally, we export the **`App`** component with the expression **`export default App;`**. This allows us to import this component into other files.

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

1. **Import React and ReactDOM Libraries:**

    ```jsx
    // index.js
    import React from 'react';
    import ReactDOM from 'react-dom/client';
    ```

    - The **`React`** and **`ReactDOM`** libraries are used to create and manage React applications.
2. **Select the Target Element in HTML:**

    ```jsx
    const el = document.getElementById('root');
    ```

    - The expression **`document.getElementById('root')`** selects an element in HTML. This represents the target element where the React application will be rendered.
3. **Create ReactDOM Root:**

    ```jsx
    const root = ReactDOM.createRoot(el);
    ```

    - The **`createRoot`** function creates the root of a React application. This manages the rendering processes of the React application.
4. **React Application Component (App):**

    ```jsx
    const el = document.getElementById('root');
    
    const root = ReactDOM.createRoot(el);
    
    function App() {
      return <h1>Hello React Learner!</h1>;
    }
    ```

    - A React functional component named **`App`** is defined. This component renders the "Hello React Learner!" heading on the screen.
5. **Render the Application:**
6.

    ```jsx
    root.render(<App />);
    ```

    - The expression **`root.render(<App />)`** renders the **`App`** component to the target element using the created **`root`**. This means the "Hello React Learner!" heading will be displayed on the page.

## Adding Props

### App.js

### **App.js**

1. **Create Main Component (App):**

    ```jsx
    jsxCopy code
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

    - Create a functional React component named **`App`**. This component represents the main structure of the page and uses the **`ProfileCard`** component to display personal digital assistants.
2. **Use Profile Cards:**

    ```jsx
    jsxCopy code
    <ProfileCard title="Alexa" handle="@alexa99" />
    <ProfileCard title="Cortana" handle="@cortana32" /><ProfileCard title="Siri" handle="@siri01" />
    
    ```

    - Use the **`ProfileCard`** component three times to create a profile card for each digital assistant. Customize each card with different titles (**`title`**) and handles (**`handle`**).

Tips and Tricks:

- You can pass dynamic data to components using props. Properties like **`title`** and **`handle`** can be dynamically changed using props passed to the **`ProfileCard`** component.
- Integrate JavaScript expressions inside JSX using curly braces **`{}`**. For example, instead of using constant values like **`title="Alexa"`**, you can use dynamic data.

### **ProfileCard.js**

1. **Define the Component and Use Props:**

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

    - Define a functional React component named **`ProfileCard`**. This component takes a **`props`** parameter. The **`props`** parameter contains the data passed to the component from the outside. In this example, it uses **`title`** and **`handle`** props to dynamically generate content.
2. **Create Dynamic Content Using Props:**

    ```jsx
    jsxCopy code
    <div>
      <div>Title is {props.title}</div><div>Handle is {props.handle}</div>
    </div>
    
    ```

    - Using curly braces **`{}`** inside JSX, access the data in props and dynamically create content. For instance, the expression **`Title is {props.title}`** concatenates the text "Title is" with the value of the **`title`** prop.

Tips and Tricks:

- The name **`props`** is commonly used to pass data to components, but you can use any other name. The important thing is to use this parameter inside the component to access external data.
- By using curly braces in JSX, you can integrate JavaScript expressions and create dynamic content, making your components more flexible and allowing them to be used with different data.

## **Using Argument Destructuring**

1. **Receive Props with Destructuring:**

    ```jsx
    jsxCopy code
    function ProfileCard({ title, handle }) { // === const { title, handle } = props; // === const title = props.title && const handle = props.handle
      return (
        <div>
          <div>Title is {title}</div>
          <div>Handle is {handle}</div>
        </div>
      );
    }
    
    ```

    - By directly destructuring the **`props`** object within the function parameters, you can access properties like **`title`** and **`handle`** directly. This makes the code shorter and more readable.
    - **`function ProfileCard({ title, handle })`** & **`const { title, handle } = props;`** & **`const title = props.title && const handle = props.handle`** all perform the same declaration.

## **Code Exercise: Practice with Props**

The project includes two components: **`App`** and **`BrightText`**.

- The **`App`** component displays three instances of the **`BrightText`** component.
- The **`BrightText`** component expects a **`color`** prop, but currently, **`App`** does not provide this prop to the three instances of **`BrightText`**.

**Goal: Add a `color` prop to the three `BrightText` elements in the `App` component.**

1. **The first color should be "red".**
2. **The second color should be "green".**
3. **The third color should be "blue".**

The **`BrightText`** component is already completed - you don't need to make any changes to it.

### **App.js**

```jsx
jsxCopy code
import React from 'react';
import BrightText from './BrightText';

function App() {
 return (
  <div>
   <BrightText color="red" />
   <BrightText color="green" />
   <BrightText color="blue" />
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

### Exercise Solution

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

## Including Images

In this React application, the **`App`** component contains three different **`ProfileCard`** components, each representing a different digital assistant.

Here are a few details and tricks:

1. **Importing Files:**
    - **`import`** statements import different components and images (**`ProfileCard`**, **`AlexaImage`**, etc.) from files. The use of **`import`** allows you to add external components or resources (images, texts) to your code.
2. **Importing Images:**
    - We also import images like **`AlexaImage`**, **`CortanaImage`**, and **`SiriImage`**. These images represent the logos of the respective digital assistants.

    ```jsx
    jsxCopy code
    import ProfileCard from './ProfileCard';
    import AlexaImage from './images/alexa.png';
    import CortanaImage from './images/cortana.png';
    import SiriImage from './images/siri.png';
    
    function App() {
     ...
    }
    
    export default App;
    
    ```

3. **Static Images:**
    - Static images typically represent image files within the project that do not change. Since these images are included in the project files, their file path is usually used as a reference.
    - Base64 is a method of encoding an image as a string. This means you can embed the image directly in the code without being dependent on an external file. It allows you to display images quickly without making HTTP requests and without the need for the user's browser to download a separate file.
4. **Dynamic Images:**
    - Dynamic images are usually obtained from external sources or as a result of user interaction. In such cases, images are often received as a base64-encoded string and displayed dynamically. This is useful, especially for quickly displaying images obtained from an API or another source without the need for the user's browser to download a separate image file.

Small Tips:

- **Advantages of Base64:**
  - Base64 is an excellent option for importing small image files, but converting large image files to base64 can increase the size of your code. Therefore, it is generally preferred for small image files or icons.
- **Async Operations in Dynamic Images:**
  - If you are asynchronously obtaining dynamic images, the conversion of the image to a base64 string can be an asynchronous operation. In this case, you need to perform appropriate operations to wait for the image to load.

## **Handling Image Accessibility**

### **App.js**

1. **Main Component:**

    ```jsx
    jsxCopy code
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

    - The main component named **`App`** contains three **`ProfileCard`** components representing profiles. Each one represents a different digital assistant.

### **ProfileCard.js**

1. **ProfileCard Component:**

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

 The **`ProfileCard`** component represents a profile card. It takes props named **`title`**, **`handle`**, and **`image`**, and renders a card using this information.

- The **`img`** tag displays the image from the **`image`** prop.

<aside>
💡 **NOTE:** If we don't add an "alt" attribute to the img element, we will encounter a warning in the 'Terminal' page.
</aside>

### **Terminal**

1. "**img elements must have an alt prop, either with meaningful text, or an empty string for decorative images jsx-a11y/alt-text**"

This warning is issued when a **`<img>`** element is used in your JSX (JavaScript XML) code, and this element lacks an **`alt`** attribute. This warning aims to ensure compliance with accessibility standards to support assistive technologies, such as screen readers.

The warning includes two scenarios:

1. **Meaningful Text:** The **`alt`** attribute of the **`<img>`** element should contain meaningful text that describes the content of the image. This provides an explanation to the user when the image fails to load or when access to the image is not available.

    ```jsx
    jsxCopy code
    jsxCopy code
    <img src="path/to/image.jpg" alt="A beautiful landscape" />
    
    ```

2. **Empty String (Decorative Images):** If the image is merely a decorative element and does not impact the meaning or content of the page, the **`alt`** attribute can be set as an empty string (**`""`**).

    ```jsx
    jsxCopy code
    jsxCopy code
    <img src="path/to/decorative-image.jpg" alt="" />
    
    ```

This warning is important to enhance the accessibility of your web application and improve the user experience. If images contain important information or are crucial for understanding the content of the page, the **`alt`** attribute should be set appropriately.

## **Adding CSS Libraries with NPM**

1. **`npm install bulma`**: This command is used to add a CSS framework named Bulma to your project. Bulma is a modern and user-friendly CSS framework that includes ready-to-use CSS classes for page layout, components, forms, and other UI elements.

    This command, executed through npm (Node Package Manager), downloads and makes Bulma available for use in your project. It adds Bulma to your project's dependencies, allowing you to use Bulma's styles and components in your project.

    After running this command, Bulma's files and folders (under **`node_modules`**) will be present in the root directory of your project. You can use these files in your project to leverage the CSS classes and components provided by Bulma. By using the CSS classes and components offered by Bulma in your HTML files, you can easily create a customized and stylish user interface.

2. **Importing Bulma:**

    ```jsx
    jsxCopy code
    import 'bulma/css/bulma.css';
    
    ```

- At the top of the code, we import the Bulma style file to make the Bulma CSS framework's styles available for use in the browser.

1. **Using Bulma Styles:**
    - The style rules provided by Bulma can be used to style other components within the application. These style rules are defined within the **`bulma.css`** file.

Tips and Tricks:

- **Quick Styling:**
  - This is a quick styling method, especially useful for those who may not have extensive knowledge of styling. CSS frameworks like Bulma can expedite the development process by providing elegant and ready-to-use styling rules.
- **Modular Development:**
  - CSS frameworks can be used to combine and develop the application style modularly with other components. This can aid in better style management and maintaining a more organized application.

## **A Big Pile of HTML**

### **ProfileCard.js**

1. **Bulma CSS Styles:**
    - Using the **`className`** property, we apply Bulma CSS framework styles to arrange the appearance of the card and its contents. For example, Bulma classes like **`card`**, **`card-image`**, **`image`**, **`title`**, **`subtitle`** are used to apply specific styling rules.
2. **Component Content:**
    - The content of the component structures the card's interior using Bulma classes. Classes such as **`card`**, **`card-image`**, **`image`**, **`card-content`**, **`media-content`**, **`title`**, **`subtitle`** are used to style the appearance.

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

Small Tips:

- **Dynamic Content:**
  - The component generates dynamic content based on the data from **`title`**, **`handle`**, and **`image`** props. This provides flexibility to use the same component with different data.

### **App.js**

1. **Bulma CSS Framework:**

    ```jsx
    jsxCopy code
    import 'bulma/css/bulma.css';
    
    ```

    - The application uses the Bulma CSS framework's styling rules to create its appearance. The **`bulma.css`** file contains Bulma styling rules, and these rules are applied throughout the application.
2. **Title and Structure:**

    ```jsx
    jsxCopy code
    <h1 className="title is-1 has-text-centered">Personal Digital Assistants</h1>
    <div className="container">
      <section className="section">
        <div className="columns">
          {/* ... */}
        </div>
      </section>
    </div>
    
    ```

    - The application's title and basic structure are arranged using Bulma styling rules. Bulma classes like **`title`**, **`container`**, **`section`**, and **`columns`** apply specific style features.

Small Tips:

- **Grid Structure:**
  - The page is organized based on Bulma's grid structure using the **`columns`** and **`column`** classes. This divides the page into columns and aligns the contents.
- **Title Style:**
  - The title is centrally aligned and given a specific style using Bulma's **`title`** and **`has-text-centered`** classes.

## **Last Bit of Styling**

This React application is designed using the Bulma CSS framework and includes profile cards representing three different digital assistants. Here's a brief explanation of this code snippet:

### **App.js**

1. **Hero Component:**

    ```jsx
    jsxCopy code
    <section className="hero is-primary">
      <div className="hero-body">
        <h1 className="title is-1 has-text-centered">Personal Digital Assistants</h1>
      </div>
    </section>
    
    ```

    - This is a Bulma hero component that forms the title section of the page. The **`is-primary`** class determines the color theme of the title.
2. **Profile Cards and Descriptions:**

    ```jsx
    <ProfileCard title="Alexa" handle="@alexa99" image={AlexaImage} description="Alexa was created by Amazon and helps you buy things" />
    {/* Benzer şekilde Cortana ve Siri için */}
    ```

- Each profile card takes a title (**`title`**), a handle (**`handle`**), an image (**`image`**), and a description (**`description`**). This creates cards with a short description for each digital assistant.

1. **Descriptions and Dynamic Content:**
    - Each profile card can be customized with different descriptions. This demonstrates the application's ability to show dynamic content and pass various data (props) to components.
2. **Responsive Design:**
    - Bulma's **`columns`** and **`column`** classes divide the page into columns and organize content in a responsive way. This allows the application to adapt to different screen sizes.

Small Tips:

- **Usage of Hero Component:**
  - The **`hero`** and **`hero-body`** classes are used to emphasize the title section. The **`is-primary`** class determines the color of the title section.
- **Adding Descriptions:**
  - By adding descriptions to profile cards, a brief description of each digital assistant is provided, offering more information to the user.
- **Bulma Grid Structure:**
  - The **`columns`** and **`column`** classes divide the page into columns. This improves the responsive design of the page and adapts it to different screen sizes.

### **ProfileCard.js**

This React component includes a simple and customizable card structure representing a digital assistant's profile card. Here's the code explanation and some small tricks:

1. **Adding Card Component and Image:**

    ```jsx
    jsxCopy code
    <div className="card">
      <div className="card-image">
        <figure className="image is-1by1">
          <img src={image} alt={title} />
        </figure>
      </div>
    </div>
    
    ```

    - The basic structure of the card includes an image within a **`card-image`** under the **`card`** class. The **`image`** class sets the aspect ratio of the image.
2. **Adding Title and Subtitle:**

    ```jsx
    jsxCopy code
    <div className="card-content">
      <div className="media-content">
        <p className="title is-4">{title}</p>
        <p className="subtitle is-6">{handle}</p>
      </div>
    </div>
    
    ```

    - The **`card-content`** class creates the content of the card. It contains the title (**`title`**) and subtitle (**`handle`**) within **`media-content`**. The **`title`** and **`subtitle`** classes determine the style of the text.
3. **Adding Description:**

    ```jsx
    jsxCopy code
    <div className="content">{description}</div>
    
    ```

    - The **`content`** class is located at the bottom of the card and contains the description. This provides more information on the card.
4. **Using Props:**
    - By using destructuring like **`{ title, handle, image, description }`**, we can pass these properties from outside to the component. This allows the component to be reusable with different data.
5. **Responsive Design:**
    - Bulma's classes like **`is-1by1`**, **`is-4`**, and **`is-6`** set the size and layout of the image and text elements. This helps the card display responsively.

Small Tips:

- **Usage of Media Content:**
  - The **`media-content`** class contains the title and subtitle, displaying text elements neatly.
- **Destructuring Props:**
  - Using **`{ title, handle, image, description }`**, the component directly resolves props, making the code more readable and concise.
- **Responsive Design Classes:**
  - Bulma's responsive design classes allow elements to adapt to different screen sizes.
