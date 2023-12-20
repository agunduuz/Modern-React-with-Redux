# State: How to Change Your App

## Initial App Setup

1. We are creating our project files:

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

## Introducing the Event System

1. **Creating a Functional Component:**
    - The statement **`function App()`** creates a functional React component. This component is the fundamental component of the application.
2. **Tracking and Logging Click Events:**
    - An arrow function named **`handleClick`** is defined. This function runs when the button is clicked and logs the message 'click' to the console.
3. **Adding a Button and Binding the Click Event:**
    - The **`<button>`** element creates a clickable button. The **`onClick`** prop determines the function to be called when the button is clicked. In this example, it's bound to the **`handleClick`** function.
4. **Defining the Function with Arrow Function:**
    - The statement **`const handleClick = () => { ... }`** defines an arrow function. Arrow functions are used to define functions concisely and clearly.
5. **Exporting the Component:**
    - The statement **`export default App;`** makes the **`App`** function exportable for use in other files. This way, you can import this component in other files.

Useful Tips:

- **Using Arrow Functions:**
  - Defining the function as an arrow function with **`const handleClick = () => { ... }`** allows you to perform the operation in a concise and understandable way.
- **Using onClick Prop:**
  - Setting **`onClick={handleClick}`** to specify the function to be called when the button is clicked forms the foundation for interactive operations in your application.
- **Using Console.log:**
  - The **`console.log('click');`** statement allows you to perform basic debugging by logging a message to the browser console.

## Kodlama Alıştırması: **Exercise with Events**

- **Objective:** Add a click event handler to the button element.
- Ensure that every time the button is clicked, you log a message to **`console.log`** saying "Hello!"

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

### Exercise Solution

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

## Introducing the State System

1. **Using State:**

    ```jsx
    import { useState } from 'react';
    ```

    - The **`useState`** function enables state management in React applications. In this example, it creates a state named **`count`**, and the **`setCount`** function is used to update this state.
2. **Setting the Initial State Value:**

    ```jsx
    const [count, setCount] = useState(0);
    ```

    - The **`useState(0)`** expression sets the initial value of the **`count`** state to 0. It also defines the **`setCount`** function that will be used to update this state.
3. **Tracking Click Event and Updating State:**

    ```jsx
    const handleClick = () => {
      setCount(count + 1);
    };
    ```

    - The **`handleClick`** function is called when the button is clicked, and it increments the **`count`** state using **`setCount`**.
4. **Using State in JSX:**

    ```jsx
    <div>Number of animals: {count}</div>
    ```

    - The expression **`{count}`** inside JSX displays the current value of the **`count`** state on the screen.
5. **Defining State with useState:**
    - Defining state using **`const [count, setCount] = useState(0);`** utilizes the **`useState`** hook, a React hook, for state management.
6. **Updating State with State Update Function:**
    - Updating the **`count`** state is done using the **`setCount`** function, as in **`setCount(count + 1);`**. This is a common approach in React for state updates.

Useful Tips:

- **Fundamental Concept of State Usage:**
  - The **`useState`** hook enables state management in React applications, allowing for dynamic and interactive behavior.
- **State Update Function:**
  - State updates involve performing an operation between the current state value and the new value. In this example, **`setCount(count + 1);`** increments the count.
- **Using Variables in JSX:**
  - The **`{count}`** expression within JSX allows you to encapsulate JavaScript expressions and dynamically display values on the screen.

## Picking a Random Element

1. **`import` Statement**: The code is importing a function named **`useState`** from the React library. The **`useState`** function is used to manage the local state of a component.
2. **`getRandomAnimal` Function**: This function returns a random animal name from a predefined list of animals. The **`Math.random()`** function generates a random number, and this number is used as an index in an array after being rounded to the nearest lower integer using **`Math.floor()`**.
3. **`App` Function Component**: This is the main component of the application. React builds user interfaces from components. This component defines the appearance and behavior of the application.
4. **Usage of State**: Using **`useState`**, a state variable named **`animals`** is created along with a **`setAnimals`** function to update it. Initially, **`animals`** is defined as an empty array.
5. **`handleClick` Function**: This function is triggered when the user clicks the button. The function adds a new animal, obtained using the **`getRandomAnimal`** function, to the current **`animals`** array. The **`setAnimals`** function assigns this new array to the **`animals`** state, causing the component to re-render.
6. **JSX Return**: The **`App`** component returns a structure in JSX (JavaScript XML) format, resembling HTML. This structure includes a button and a **`div`** that displays the **`animals`** array. The button is associated with the **`handleClick`** function.
7. **`export default App;`**: This statement exports the **`App`** component, making it usable in other files.

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

**Important React Concept:**

- **Declarative Approach**: React uses a declarative approach. This means that the current state of the application, as well as the states and properties (props) of components, are defined. When these states or properties change, React automatically updates the interface.

## **List Building in React**

### **`App.js` File**

This file contains the main component of the application (**`App`**).

1. **Imports**: **`useState`** is imported from React, and **`AnimalShow`** is imported from a local file. **`AnimalShow`** is another component and will be used in this file.
2. **`getRandomAnimal` Function**: This is a helper function that returns a random animal name, as explained earlier.
3. **State and Event Handler**: Using **`useState`**, a state variable named **`animals`** is defined, and **`setAnimals`** is used to update this state. The **`handleClick`** function updates this state by adding new animals.
4. **`renderedAnimals` Variable**: This variable creates an array of JSX elements by calling the **`AnimalShow`** component for each element in the **`animals`** array. Each **`AnimalShow`** component is given the animal name as a **`type`** prop and a unique key (in this case, the array index) as a **`key`** prop.
5. **JSX Return**: The **`App`** component returns a structure in JSX format, consisting of a button and the **`renderedAnimals`** array. The button is associated with the **`handleClick`** function and adds a new animal on each click.

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

### **`AnimalShow.js` File**

This file contains another component named **`AnimalShow`**.

1. **Function Component**: **`AnimalShow`** is a function component. It takes **`type`** as a prop, which is the **`type`** prop passed to the **`AnimalShow`** component in the **`App.js`** file.
2. **JSX Return**: This component displays the **`type`** prop it receives within a **`div`** element. In other words, it shows the animal name from the **`type`** prop on the screen.

```jsx
function AnimalShow({ type }) {
  return <div>{type}</div>;
}
export default AnimalShow;
```

### **Relationship and Communication**

- In the **`App.js`** file, the **`AnimalShow`** component is called multiple times within **`renderedAnimals`** using the **`map`** function. Each call passes an animal name as the **`type`** prop.
- **`AnimalShow`** receives this prop and displays it on the screen. This way, data created within the **`App`** component (the **`animals`** list) is used and displayed by another component, **`AnimalShow`**.

## **Loading and Showing SVGs**

At the beginning of the code, SVG files for various animals are imported. These SVG files are located in the **`./svg/`** directory, with a separate file for each animal. React allows you to import static files (images, SVG files, etc.) using module bundlers like Webpack.

```jsx
import bird from './svg/bird.svg';
import cat from './svg/cat.svg';
// diğer hayvanlar için benzer içe aktarmalar
```

### **`svgMap` Object**

This object contains animal names as keys and their respective SVG files as values. This structure allows us to easily find the relevant SVG based on animal names.

```jsx
const svgMap = { bird, cat, cow, dog, gator, horse };
```

### **`AnimalShow` Component**

AnimalShow is a function component that takes a prop named type. This type specifies which animal will be displayed

```jsx
function AnimalShow({ type }) {
  return (
    <div>
      <img alt="animal" src={svgMap[type]} />
    </div>
  );
}
```

### **Displaying the Image**

- The component selects the appropriate SVG file from the **`svgMap`** object based on the **`type`** prop and displays it within an **`img`** tag.
- The **`src={svgMap[type]}`** expression determines the path to the correct SVG file based on the **`type`** value.
- The **`alt="animal"`** expression defines the alternate text for the image. This is important for accessibility and is displayed if the image cannot be loaded or when screen readers are used.

## **Increasing Image Size**

1. **Import Statements**: **`import`** statements allow you to load variables or modules from other files that you want to use. For example, the line **`import bird from './svg/bird.svg';`** loads the **`bird.svg`** file from the **`svg`** folder in the same directory.
2. **Functional Component**: In this code, a functional component named **`AnimalShow`** is defined. React uses such components to define how the UI will look.
3. **Props**: The **`AnimalShow`** component receives a prop named **`type`**. Props are used to pass data to components. Here, the **`type`** prop determines which animal to display.
4. **useState Hook**: **`useState`** is a React Hook that enables state management within a component. The line **`const [clicks, setClicks] = useState(0);`** creates a state variable named **`clicks`** and a function (**`setClicks`**) to update it.
5. **Event Handling**: The **`handleClick`** function captures user clicks and updates the **`clicks`** state.
6. **Rendering**: The component renders the UI using JSX (JavaScript XML). Two **`<img>`** tags are used here: one for the animal and the other for the heart. The size of the heart image changes based on the **`clicks`** state.

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

### **Tips and Tricks:**

- **Destructuring**: When using props and state variables, you can use JavaScript's destructuring feature. This makes your code cleaner and more readable.
- **Conditional Rendering**: If you want to display different UI elements for different types of animals, you can use conditional expressions within JSX.
- **Performance Optimization**: If you have performance concerns, you can prevent unnecessary renders by using techniques like **`React.memo`** or **`useMemo`**.
- **Styling**: Instead of using inline CSS styles, consider using libraries like CSS modules or styled-components for a more modular and maintainable approach to styling.

## **Adding Custom CSS**

1. **Component Structure**: There is the **`App`** main component and the **`AnimalShow`** sub-component. **`App`** serves as the entry point of the application and contains other components.
2. **Importing Styles and Components**: CSS files are loaded with **`import './App.css';`** and **`import './AnimalShow.css';`**. This allows you to define specific styles for your components. The statement **`import AnimalShow from './AnimalShow';`** loads the **`AnimalShow`** component.
3. **State Management in Parent Component**: In the **`App`** component, the application's state is managed using **`useState`**. This enables you to control how the UI changes in response to user actions. For example, there could be an "Add Animal" button, and clicking it could create a new **`AnimalShow`** component each time.
4. **Event Handling**: A click event on a button is handled using the **`onClick`** attribute. This is a fundamental way to capture user interactions.
5. **Rendering Child Components**: Within **`App`**, **`AnimalShow`** components can be rendered dynamically. This is often done using JavaScript functions like **`.map()`** on an array or list.

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

### **Tips and Tricks:**

- **Component Separation**: It's important for each component to focus on its own functionality. This improves code readability and maintainability.
- **Props Passing**: Use props for data transfer between child components. This enables data flow between components.
- **Reusable Components**: Make components reusable. For example, **`AnimalShow`** can be used for many different animal types.
- **CSS Modules or Styled Components**: Consider using approaches like CSS Modules or styled-components to prevent style conflicts.
- **State Lifting**: Sometimes, multiple child components may need to use the same data. In such cases, lifting the state to the parent component can be a good solution.
![FireShot Capture 073 - React App - localhost](https://github.com/agunduuz/Modern-React-with-Redux/assets/76620858/615199fc-83b5-4a45-830f-c56bda9016cb)

  
