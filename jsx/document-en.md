# **Creating Content with JSX**

## **Displaying Basic Content**

1. **Import React and ReactDOM Libraries:**

    ```jsx
    import React from 'react';
    import ReactDOM from 'react-dom/client';   
    ```

    - Import the React and ReactDOM libraries. React is used to create user interfaces, while ReactDOM is used to mount React applications onto HTML pages.
2. **Select Target Element in HTML:**

    ```jsx
    const el = document.getElementById('root');
    ```

    - Select an element with the id 'root' in the HTML. This element represents the target div where the React application will be rendered.
3. **Create ReactDOM Root:**

    ```jsx
    const root = ReactDOM.createRoot(el);
    ```

    - Use the **`createRoot`** function to create the root of the React application. This root manages the rendering processes.
4. **React Application Component (App):**

    ```jsx
    function App() {
      return <h1>Hello Cosmos!</h1>;
    }
    ```

    - Define a simple functional component named **`App`**. This component renders only the "Hello Cosmos!" heading.
5. **Render the Application:**

    ```jsx
    root.render(<App />);
    ```

    - Call the **`render`** method on the **`root`** to render the **`App`** component to the 'root' element. This displays the "Hello Cosmos!" heading on the page.

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

## **Printing JavaScript Variables in JSX**

1. **Create a Functional Component:**

    ```jsx
    function App() {
    ```

    - Create a functional component named **`App`**. Functional components represent the elements of the user interface in React applications.
2. **Create a Message Variable:**

    ```jsx
    let message = 'Bye There!';
    ```

    - Create a variable named **`message`** with a default value of 'Bye There!'.
3. **Randomly Select a Message:**

    ```jsx
    if (Math.random() > 0.5) {
      message = 'Hello There!';
    }
    ```

    - If the result of **`Math.random()`** is greater than 0.5, update the **`message`** variable to 'Hello There!'.
4. **Display Message in JSX:**

    ```jsx
    return <h1>{message}</h1>;
    ```

    - Use JSX to display the value of the **`message`** variable inside an **`<h1>`** heading tag. This will show either 'Hello There!' or 'Bye There!' depending on the variable's value.

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

## **Short JavaScript Expressions**

1. **First Example:**

    ```jsx
    function App() {
      const date = new Date();
      const time = date.toLocaleTimeString();
    
      return <h1>{time}</h1>;
    }
    ```

    - In this example, create a **`date`** variable and use it to get the localized time string. Display this time string in an **`<h1>`** heading tag.
2. **Second Example:**

    ```jsx
    function App() {
      return <h1>{new Date().toLocaleTimeString()}</h1>;
    }
    ```

    - In the second example, directly create a time string using the **`toLocaleTimeString()`** function and display it in an **`<h1>`** heading tag.

    **Differences and Tips:**

    - In the first example, the time is stored in a variable (**`time`**) before rendering. This can make the code more readable because the time information is named.
    - In the second example, the time is generated and displayed in a single line without storing it in a variable. This can be practical for short-lived and one-time-use variables.

## **Code Exercise: Quick Practice with JSX**

The App component below needs some modifications. It should display your name. Let's fix it!

1. Add your name to an empty string on line 4.
2. Use the **`name`** variable in the h1 element on line 6.

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

### **Exercise Solution**

```jsx
...
function App() {
 const name = 'Your Name';

 return (
  <div>
   My name is:
   <h1>{name}</h1>
  </div>
 );
}
...
```

## **Typical Component Structures**

```jsx
...
function App() {
  const name = 'John';
  const age = 30;
  return (
    <h1>
      My name is {name} and I am {age} years old.
    </h1>
  );
}
...
```

**Explanation:**

1. **Variable Declaration:** The lines **`const name = 'John';`** and **`const age = 30;`** declare two variables, **`name`** and **`age`**, containing name and age information.
2. **JSX Usage:** JSX (JavaScript XML) is used to create a text content by combining the variables. The expression **`{name}`** is replaced with the value of the **`name`** variable, and similarly for **`{age}`**.

## **Customizing Elements with Props**

```jsx
...
function App() {
  const inputType = 'number';
  const minValue = 5;
  return <input type={inputType} min={minValue} max={10} style={{ border: '3px solid #ddd' }} />;
}
...
```

**Explanation:**

1. **Variable Declaration:** The lines **`const inputType = 'number';`** and **`const minValue = 5;`** declare two variables, **`inputType`** and **`minValue`**, containing information about the input element.
2. **Creating JSX Input:** The line **`<input type={inputType} min={minValue} max={10} style={{ border: '3px solid #ddd' }} />`** creates an input element using JSX. The **`type`** attribute is set to the value of **`inputType`**, the **`min`** attribute is set to the value of **`minValue`**, and a border style is applied using the **`style`** attribute.

## **Converting HTML to JSX**

```jsx
...
function App() {
  // autoFocus={true} specifies that the input should be automatically focused when the page loads.
  return <textarea autoFocus={true} />;
}
...
```

**Explanation:**

1. **Textarea Creation:** The line **`<textarea autoFocus={true} />`** creates a textarea element using JSX. The **`autoFocus`** attribute is set to **`true`**, indicating that the textarea should be automatically focused when the page loads.
2. **Prop Naming in JSX:** In React, prop names are written in camelCase in JSX. Therefore, instead of **`auto-focus`**, it is written as **`autoFocus`**.

```jsx
...
function App() {
  // className attribute allows assigning one or more CSS classes to the element.
  return <input className="inputArea" />;
}
...
```

**Explanation:**

1. **Input Creation:** The line **`<input className="inputArea" />`** creates an input element using JSX. The **`className`** attribute is used to assign the CSS class "inputArea" to the input element.
2. **JSX Class Names:** In JSX, class names are written as **`className`** instead of **`class`** to avoid conflicts with the JavaScript keyword.

```jsx
...
function App() {
  // Inline styles are specified using an object in JSX.
  // Each style property is specified as a key-value pair within the object.
  // Style properties in JSX are written in camelCase (e.g., paddingTop instead of padding-top).
  return <input style={{ padding: '5px', marginTop: '15px' }} />;
}
...
```

**Explanation:**

1. **Styling with Inline Styles:** The line **`<input style={{ padding: '5px', marginTop: '15px' }} />`** applies inline styles to the input element using JSX. The styles are specified as an object with camelCase property names.
2. **JSX Style Properties:** In JSX, style properties are written in camelCase, unlike regular CSS. For example, **`padding-top`** becomes **`paddingTop`**.

## **Code Exercise: Practice with JSX Transformation**

Apply JSX Transformation
Remember five rules when converting HTML to JSX.

1. All prop names should adhere to camelCase usage.
2. Numeric attribute values are enclosed in curly braces.
3. Booleans that are 'true' are written using only the attribute's name.
4. The 'class' attribute is written as 'className'.
5. Inline styles are provided as an object.

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

### **Exercise Solution**

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

## **Extracting Components**

Let's first look at the **`index.js`** file:

```jsx
// index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const el = document.getElementById('root');
const root = ReactDOM.createRoot(el);

root.render(<App />);
```

1. **`import App from './App';`**: This line imports the component named **`App`** from the file './App'. This component could be the main component of the application.
2. **`const el = document.getElementById('root');`**: It selects an element with the id 'root' in the HTML document and assigns it to the variable **`el`**.
3. **`const root = ReactDOM.createRoot(el);`**: It creates a root using the **`createRoot`** function. In React 18 and later, **`createRoot`** is used to enable asynchronous rendering and concurrent mode.
4. **`root.render(<App />);`**: It renders the **`App`** component onto the **`root`**. In other words, the **`App`** component is added to the 'root' element and displayed.

Now, let's look at the **`App.js`** file:

```jsx
// App.js

function App() {
  return <h1>App Js</h1>;
}

export default App;
```

1. **`function App() { ... }`**: In this line, a simple functional component named **`App`** is defined. This component creates a user interface by returning JSX.
2. **`export default App;`**: It exports the **`App`** component. This allows us to import the **`App`** component from other files.

In summary, the **`index.js`** file sets up the beginning of the React application and uses the **`App`** component from the **`App.js`** file to display something. React provides a modular and component-focused structure, making large applications more manageable.

## **Overview of Module Systems**

1. **Module**: A unit in a JavaScript file that contains one or more functions, variables, or classes. This file can be imported (import) or exported (export) by other files.
2. **Importing and Exporting**: Module systems allow data or code to be transferred from one file to another. To send something from one file to another, use **`export`**, and to receive it, use **`import`**.

### **Example:**

1. **Person.js (Exporting):**

```jsx
// Person.js

class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Hello, I'm ${this.name}!`);
  }
}

// Exporting the Person class
export default Person;
```

**App.js (Importing):**

```jsx
// App.js

// Importing the Person class from the Person.js file
import Person from './Person';

// Creating an instance
const person1 = new Person('John', 25);

// Calling the instance method
person1.sayHello();
```

In this example, the **`Person`** class is exported from **`Person.js`** using **`export default`**. Then, in **`App.js`**, it is imported using **`import Person from './Person';`** and used to create an instance.

### **File Paths and Nested Modules:**

1. **File Paths:** In React projects, file paths are often used to express relationships between files. For example, a "components" folder may contain another "Header" folder. Using correct file paths helps reference files from one another.
2. **Nested Modules:** Projects often contain nested modules. For example, a "components" folder may contain a "Header" folder. Nested modules can reference each other using file paths.

### **Importing Multiple Functions or Variables and Exporting:**

1. **Multiple Imports (Named Imports):** To import multiple functions or variables from a file, name these items in the file and then import them using their names.

    Example:
    1. **utils.js:**

    ```jsx
    // utils.js
    
    export const add = (a, b) => a + b;
    export const subtract = (a, b) => a - b; 
    ```

    - In this module, two functions (**`add`** and **`subtract`**) are defined and exported using the **`export`** keyword. This allows other modules to import these functions.
  
2. **App.js:**

    ```jsx
    // App.js
    
    import { add, subtract } from './utils';
    
    console.log(add(5, 3)); // 8
    console.log(subtract(5, 3)); // 2
    ```

    - In the **`App.js`** module, the **`add`** and **`subtract`** functions are imported from the **`utils.js`** module using the **`{ add, subtract }`** syntax. This is known as named import, where you specifically import the functions you need.

### **Import Everything as an Alias:**

1. **utils.js:**

    ```jsx
    // utils.js
    
    export const add = (a, b) => a + b;
    export const subtract = (a, b) => a - b;
    
    ```

    - Similar to before, the **`add`** and **`subtract`** functions are defined and exported.

2. **App.js:**

    ```jsx
    // App.js
    
    import * as utils from './utils';
    
    console.log(utils.add(5, 3)); // 8
    console.log(utils.subtract(5, 3)); // 2
    ```

    - In this example, the **`as utils`** syntax is used to import all exports from **`utils.js`** and alias them as **`utils`**. This way, you access the functions using **`utils.add`** and **`utils.subtract`**.

### **Notes:**

- The use of modules helps organize code, making it more maintainable and scalable.
- File paths (**`'./utils'`**) are used to specify the location of the modules.
- The **`export default`** syntax is not used in these examples, but it's another way to export a single value or function from a module.
- Module systems are crucial for managing dependencies and structuring code in larger applications.
