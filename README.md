# React & JavaScript Interview Preparation

Welcome to the **React & JavaScript Interview Preparation** repository! This repo contains resources, guides, and practice questions designed to help you prepare for your React and JavaScript interviews. Whether you're a beginner or looking to level up your skills, you'll find valuable content here to aid in your journey.

## Table of Contents

- [Introduction](#introduction)
- [JavaScript Preparation](#javascript-preparation)
  - [JavaScript Output-Based Questions](#javascript-output-based-questions)
- [React Preparation](#react-preparation)
  - [React Component Lifecycle](#react-component-lifecycle)
- [What's Coming Next](#whats-coming-next)
- [Contributing](#contributing)

## Introduction

This repository is a collection of **interview preparation** materials specifically for React and JavaScript. It includes explanations of concepts, important interview questions, and more. As the repository grows, more sections will be added to help you fully prepare for React and JavaScript interviews!

## JavaScript Preparation

### JavaScript Output-Based Questions

In this section, you'll find **JavaScript output-based interview questions** that test your understanding of how JavaScript executes code. These questions are focused on scenarios that involve tricky behavior with variables, functions, scoping, closures, and asynchronous operations.

#### Examples:

- **Question 1**: What will be the output of the following code?
  ```javascript
  var x = 10;
  setTimeout(function() {
    console.log(x);
  }, 0);
  var x = 20;
  ```
  *Expected Output:* `20`

- **Question 2**: What will be the output of the following code?
  ```javascript
  function foo() {
    console.log(bar);
    var bar = 2;
  }
  foo();
  ```
  *Expected Output:* `undefined`

- **Question 3**: What will be the output of the following code?
  ```javascript
  let x = 1;
  function test() {
    console.log(x);
    let x = 2;
  }
  test();
  ```
  *Expected Output:* `ReferenceError: Cannot access 'x' before initialization`

(Feel free to add more questions as you build this section.)

## React Preparation

### React Component Lifecycle

This section covers the **React component lifecycle** for class components. Understanding the lifecycle methods is key for handling side effects, fetching data, and managing state in React.

#### Key Lifecycle Methods:
- **`componentDidMount()`**: Called after the component is mounted in the DOM. Good for fetching data or starting timers.
- **`componentDidUpdate()`**: Called after the component updates due to state or props changes. Used for responding to state/prop changes.
- **`componentWillUnmount()`**: Called just before the component is unmounted from the DOM. Useful for cleanup (e.g., removing event listeners or clearing timers).
- **`shouldComponentUpdate()`**: Allows you to optimize performance by preventing unnecessary renders.

### Example (Class Component Lifecycle):
```javascript
class MyComponent extends React.Component {
  componentDidMount() {
    console.log('Component Mounted');
  }

  componentDidUpdate(prevProps, prevState) {
    console.log('Component Updated');
  }

  componentWillUnmount() {
    console.log('Component Will Unmount');
  }

  render() {
    return <div>React Lifecycle Methods</div>;
  }
}
```

As you work through React interview questions, we'll cover hooks and other modern concepts in upcoming sections.

## What's Coming Next

This repository is a **work in progress**, and additional topics and sections will be added over time. Here's what you can expect in future updates:

- **Advanced JavaScript Topics**
  - Asynchronous JavaScript (Promises, Async/Await, Event Loop)
  - Closures, Hoisting, and Scopes
  - JavaScript Algorithms and Data Structures
  - More output-based questions

- **React Topics**
  - React Hooks (useState, useEffect, useContext, useReducer)
  - Functional Components vs Class Components
  - State Management (Redux, Context API)
  - React Patterns (Higher Order Components, Render Props)

- **Coding Challenges and Solutions**
  - Leetcode, Codewars, and other coding challenge platforms

Check back regularly for updates as more resources are added to this repo!

## Contributing

Contributions are welcome! If you'd like to contribute to this repo, please fork it and submit a pull request. Be sure to follow the contribution guidelines and ensure that your code follows the style of the repository.
