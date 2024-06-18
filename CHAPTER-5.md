# Chapter 5: Modern JavaScript Syntax and Features

### The Importance of Decoupling Applications
- Modular - set of highly decoupled, distinct pieces of functionality stored in modules
- Remove dependecies
- JS modules

Example
```javascript
// utils.js
export const add = (a, b) => {
  return a + b
}

export const subtract = (a, b) => {
  return a - b
} 

// index.js
import { add } from './utils' // Only import what you need

console.log(add(1,2)) // print 3
```

### Dynamic Imports
- Lazy-loading modules allows you to load what you need when needed
- Example: when user clicks a link or a button => load a module
- Function-like form of import `import(url)`

Example:
```javascript
// cakeFactory.js

export function bakeCake() {
  console.log('Baking a delicious cake!');
}

// Function to dynamically import the cakeFactory module
document.getElementById('loadButton').addEventListener('click', async () => {
  try {
    let module = await import('/modules/cakeFactory.js');
    module.bakeCake();
  } catch (error) {
    console.error('Error loading the cakeFactory module:', error);
  }
});
```

### Modules for the Server
- Node 15.3.0 onward supports JS modules
```javascript
{
  ...otherConfig
  "type": "module"
}
```

### Advantages of Using Modules
- Modules are auto-deferred
- Easy to maintain and use
- Provide namespacing

### Classes with Constructors, Getters, and Setters
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes

### Reference
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules
