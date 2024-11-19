
# JavaScript Interview Questions (Medium to Medium-Hard)

This document contains 50 JavaScript interview questions with their outputs and explanations. These questions cover a variety of concepts, including closures, hoisting, scoping, asynchronous behavior, and more.

---

### 1. **What will the following code output?**
   ```javascript
   console.log(0.1 + 0.2 === 0.3);
   ```

   **Output:** `false`
   
   **Reason:** Floating-point arithmetic in JavaScript can lead to precision issues. `0.1 + 0.2` results in a value that's slightly more than `0.3`, so the comparison fails.

---

### 2. **What will be the output of this code?**
   ```javascript
   var a = 10;
   (function() {
       console.log(a);
       var a = 20;
   })();
   ```

   **Output:** `undefined`
   
   **Reason:** Due to JavaScript hoisting, the variable `a` inside the function is hoisted, but its value is not assigned until after the `console.log()` call.

---

### 3. **What will this code output?**
   ```javascript
   var a = 10;
   (function() {
       a = 20;
       console.log(a);
   })();
   console.log(a);
   ```

   **Output:**
   ```
   20
   20
   ```
   
   **Reason:** The inner function modifies the global `a` because there is no `var`, `let`, or `const` within the function, so it updates the global variable.

---

### 4. **What will this code output?**
   ```javascript
   var a = 1;
   function test() {
       console.log(a);
       var a = 2;
   }
   test();
   ```

   **Output:** `undefined`
   
   **Reason:** The variable `a` inside the function is hoisted, but its value is not assigned until after the `console.log()`.

---

### 5. **What will the following code output?**
   ```javascript
   let x = 1;
   function foo() {
       let x = 2;
       console.log(x);
   }
   foo();
   ```

   **Output:** `2`
   
   **Reason:** The function `foo()` has its own local variable `x`, which shadows the global variable. Thus, `2` is logged.

---

### 6. **What will this code output?**
   ```javascript
   var foo = 'foo';
   function test() {
       console.log(foo);
       var foo = 'bar';
   }
   test();
   ```

   **Output:** `undefined`
   
   **Reason:** The `foo` variable inside `test()` is hoisted and is `undefined` during the `console.log()` call.

---

### 7. **What will the following code output?**
   ```javascript
   var i = 10;
   setTimeout(function() {
       console.log(i);
   }, 1000);
   var i = 20;
   ```

   **Output:** `20`
   
   **Reason:** JavaScript's event loop ensures that the `setTimeout` callback is executed after the synchronous code is finished, so `i` is 20 when logged.

---

### 8. **What will be the output of this code?**
   ```javascript
   console.log(typeof null);
   ```

   **Output:** `object`
   
   **Reason:** In JavaScript, `null` is considered an object due to a historical bug, which remains for backward compatibility.

---

### 9. **What will this code output?**
   ```javascript
   console.log(1 + '1');
   ```

   **Output:** `'11'`
   
   **Reason:** The `+` operator with a string and a number triggers string concatenation, so `1 + '1'` becomes `'11'`.

---

### 10. **What will the following code output?**
   ```javascript
   console.log(1 - '1');
   ```

   **Output:** `0`
   
   **Reason:** JavaScript coerces the string `'1'` into a number, so `1 - 1` results in `0`.

---

### 11. **What will this code output?**
   ```javascript
   let a = [1, 2];
   let b = a;
   b[0] = 100;
   console.log(a);
   ```

   **Output:** `[100, 2]`
   
   **Reason:** Arrays are reference types, so both `a` and `b` point to the same array in memory. Modifying `b` affects `a`.

---

### 12. **What will this code output?**
   ```javascript
   let a = {};
   let b = { key: 'value' };
   console.log(a == b);
   ```

   **Output:** `false`
   
   **Reason:** Objects in JavaScript are compared by reference, not by value, so `a` and `b` are not the same object.

---

### 13. **What will the following code output?**
   ```javascript
   function test() {
       return
       {
           key: 'value'
       };
   }
   console.log(test());
   ```

   **Output:** `undefined`
   
   **Reason:** JavaScript automatically inserts a semicolon after `return`, so the function returns `undefined` instead of the object.

---

### 14. **What will the following code output?**
   ```javascript
   let arr = [1, 2, 3];
   arr.length = 2;
   console.log(arr);
   ```

   **Output:** `[1, 2]`
   
   **Reason:** Changing the `length` property of an array truncates it, so only the first two elements are kept.

---

### 15. **What will be the output of the following code?**
   ```javascript
   var a = [1, 2, 3];
   var b = [...a];
   b.push(4);
   console.log(a);
   console.log(b);
   ```

   **Output:**
   ```
   [1, 2, 3]
   [1, 2, 3, 4]
   ```
   
   **Reason:** The spread operator creates a shallow copy of the array, so `a` is unaffected by changes to `b`.

---

### 16. **What will this code output?**
   ```javascript
   console.log([] == ![]);
   ```

   **Output:** `true`
   
   **Reason:** `[]` is coerced to a falsy value, and `![]` evaluates to `false`. Then, `false` is coerced to an empty string, which is loosely equal to `[]`.

---

### 17. **What will the following code output?**
   ```javascript
   console.log({} + {});
   ```

   **Output:** `[object Object][object Object]`
   
   **Reason:** When an object is used with `+`, JavaScript converts it to a string using its `toString()` method, which defaults to `[object Object]`.

---

### 18. **What will be the output of this code?**
   ```javascript
   function test(a = 1, b = 2) {
       return a + b;
   }
   console.log(test());
   ```

   **Output:** `3`
   
   **Reason:** Default parameters are used when the argument is not provided, so `a = 1` and `b = 2`.

---

### 19. **What will the following code output?**
   ```javascript
   var a = 5;
   var b = a++;
   console.log(a);
   console.log(b);
   ```

   **Output:**
   ```
   6
   5
   ```
   
   **Reason:** The post-increment operator `a++` returns the original value of `a` before incrementing it.

---

### 20. **What will this code output?**
   ```javascript
   var a = 5;
   var b = ++a;
   console.log(a);
   console.log(b);
   ```

   **Output:**
   ```
   6
   6
   ```
   
   **Reason:** The pre-increment operator `++a` increments `a` first and then assigns the new value to `b`.

---

### 21. **What will be the output of this code?**
   ```javascript
   function test(a = 1, b = 2) {
       return a + b;
   }
   console.log(test());
   ```

   **Output:** `3`
   
   **Reason:** Default parameters are used when the argument is not provided, so `a = 1` and `b = 2`.

---

### 22. **What will the following code output?**
   ```javascript
   console.log([1] == 1);
   console.log([1] === 1);
   ```

   **Output:**
   ```
   true
   false
   ```
   
   **Reason:** The `==` operator performs type coercion, so `[1]` is compared to `1` and coerced to `true`. The `===` operator, however, checks for strict equality, and objects are never strictly equal to primitive values.

---

### 23. **What will this code output?**
   ```javascript
   var a = [1, 2, 3];
   var b = a;
   b = [4, 5, 6];
   console.log(a);
   console.log(b);
   ```

   **Output:**
   ```
   [1, 2, 3]
   [4, 5, 6]
   ```
   
   **Reason:** `b` is reassigned to a new array `[4, 5, 6]`, so it no longer points to the original array `a`.

---

### 24. **What will this code output?**
   ```javascript
   console.log([] + []);
   ```

   **Output:** `""`
   
   **Reason:** Both arrays are empty, and when arrays are concatenated with `+`, they are coerced into empty strings, resulting in an empty string.

---

### 25. **What will the following code output?**
   ```javascript
   function test() {
       console.log(arguments.length);
   }
   test(1, 2, 3);
   ```

   **Output:** `3`
   
   **Reason:** The `arguments` object is an array-like object that contains all the arguments passed to the function, so `arguments.length` is `3`.

---

### 26. **What will this code output?**
   ```javascript
   function foo() {
       return { key: 'value' };
   }
   console.log(foo());
   ```

   **Output:** `{ key: 'value' }`
   
   **Reason:** The function returns an object literal `{ key: 'value' }`. Since there is no ambiguity with the return statement, the object is returned successfully.

---

### 27. **What will the following code output?**
   ```javascript
   let x = 10;
   let y = 20;
   let z = (x, y) => x + y;
   console.log(z(30, 40));
   ```

   **Output:** `70`
   
   **Reason:** The arrow function returns the result of `x + y`. The arguments `30` and `40` are passed to `x` and `y`, respectively.

---

### 28. **What will this code output?**
   ```javascript
   var num = 5;
   var double = (num) => num * 2;
   console.log(double(num));
   ```

   **Output:** `10`
   
   **Reason:** The variable `num` is passed to the arrow function, which returns its double (i.e., `5 * 2`).

---

### 29. **What will the following code output?**
   ```javascript
   var myObject = {
       name: "John",
       age: 30
   };
   var clone = Object.assign({}, myObject);
   clone.name = "Jane";
   console.log(myObject.name);
   ```

   **Output:** `John`
   
   **Reason:** `Object.assign()` creates a shallow copy of `myObject`. The name property is modified in `clone`, but `myObject` remains unchanged because the `name` property is a primitive value.

---

### 30. **What will the following code output?**
   ```javascript
   function test() {
       console.log(this);
   }
   test();
   ```

   **Output:** Depends on context
   - In **non-strict mode**, it logs the global object (e.g., `window` in browsers).
   - In **strict mode**, it logs `undefined`.

   **Reason:** In non-strict mode, `this` refers to the global object when used in a regular function. In strict mode, `this` is `undefined`.

---

### 31. **What will the following code output?**
   ```javascript
   const obj = {
       name: 'Alice',
       greet: function() {
           console.log(`Hello, ${this.name}`);
       }
   };
   obj.greet();
   ```

   **Output:** `Hello, Alice`
   
   **Reason:** The `greet()` method is invoked on `obj`, so `this` refers to the `obj` and `this.name` resolves to `'Alice'`.

---

### 32. **What will be the output of this code?**
   ```javascript
   const person = {
       firstName: 'John',
       lastName: 'Doe',
       fullName: function() {
           return this.firstName + ' ' + this.lastName;
       }
   };
   const member = { firstName: 'Jane', lastName: 'Smith' };
   console.log(person.fullName.call(member));
   ```

   **Output:** `Jane Smith`
   
   **Reason:** `call()` allows you to invoke the method `fullName` with a different `this` value, so `this.firstName` and `this.lastName` refer to `member`.

---

### 33. **What will this code output?**
   ```javascript
   function bar() {
       console.log(this);
   }
   const obj = { bar };
   obj.bar();
   ```

   **Output:** `obj`
   
   **Reason:** When `bar()` is called as a method of `obj`, `this` refers to the object `obj`.

---

### 34. **What will this code output?**
   ```javascript
   function greet() {
       console.log('Hello, ' + this.name);
   }
   const person = { name: 'Alice' };
   greet.call(person);
   ```

   **Output:** `Hello, Alice`
   
   **Reason:** `call()` binds `this` to the `person` object, so `this.name` refers to `Alice`.

---

### 35. **What will the following code output?**
   ```javascript
   var x = 10;
   (function() {
       var x = 20;
       (function() {
           var x = 30;
           console.log(x);
       })();
   })();
   ```

   **Output:** `30`
   
   **Reason:** The innermost function has its own local variable `x`, and it is logged when the `console.log(x)` statement is executed.

---

### 36. **What will this code output?**
   ```javascript
   let x = 10;
   function outer() {
       let x = 20;
       function inner() {
           console.log(x);
       }
       inner();
   }
   outer();
   ```

   **Output:** `20`
   
   **Reason:** The `inner` function accesses the `x` variable from its enclosing `outer()` function, where `x` is `20`.

---

### 37. **What will this code output?**
   ```javascript
   var name = "John";
   function test() {
       console.log(name);
       var name = "Doe";
   }
   test();
   ```

   **Output:** `undefined`
   
   **Reason:** The `name` variable inside the function is hoisted and initialized as `undefined` before being assigned `"Doe"`.

---

### 38. **What will the following code output?**
   ```javascript
   function sum(a, b = 1) {
       return a + b;
   }
   console.log(sum(5));
   ```

   **Output:** `6`
   
   **Reason:** The parameter `b` has a default value of `1`, so when `5` is passed for `a`, the sum is `5 + 1`.

---

### 39. **What will this code output?**
   ```javascript
   const arr = [1, 2, 3];
   arr.length = 2;
   console.log(arr);
   ```

   **Output:** `[1, 2]`
   
   **Reason:** Changing the `length` property of an array truncates the array, leaving only the first two elements.

---

### 40. **What will the following code output?**
   ```javascript
   var a = '10';
   var b = 10;
   console.log(a == b);
   console.log(a === b);
   ```

   **Output:**
   ```
   true
   false
   ```
   
   **Reason:** The `==` operator performs type coercion, so the string `'10'` is compared to the number `10`. The `===` operator checks for strict equality, so it returns `false`.

---

### 41. **What will this code output?**
   ```javascript
   let a = [1, 2, 3];
   let b = a;
   b.push(4);
   console.log(a);
   ```

   **Output:** `[1, 2, 3, 4]`
   
   **Reason:** Arrays are reference types, so when `b.push(4)` is called, it modifies the array `a` because both `a` and `b` refer to the same array.

---

### 42. **What will the following code output?**
   ```javascript
   let arr = [1, 2, 3];
   arr[5] = 10;
   console.log(arr);
   ```

   **Output:** `[1, 2, 3, <2 empty items>, 10]`
   
   **Reason:** When assigning a value to an index that is not yet defined, JavaScript fills in the "gap" with empty items.

---

### 43. **What will this code output?**
   ```javascript
   let person = { name: 'John', age: 30 };
   let clone = { ...person };
   console.log(clone);
   ```

   **Output:**
   ```
   { name: 'John', age: 30 }
   ```
   
   **Reason:** The spread operator (`...`) creates a shallow copy of the `person` object, so the `clone` object is a copy of `person` with the same properties.

---

### 44. **What will the following code output?**
   ```javascript
   const obj1 = { name: 'Alice' };
   const obj2 = { ...obj1, age: 25 };
   console.log(obj2);
   ```

   **Output:**
   ```
   { name: 'Alice', age: 25 }
   ```
   
   **Reason:** The spread operator copies the properties from `obj1` into `obj2`, and the property `age: 25` is added to `obj2`. The resulting object contains both `name` and `age`.

---

### 45. **What will this code output?**
   ```javascript
   let num = [1, 2, 3];
   let [a, b, c] = num;
   console.log(a, b, c);
   ```

   **Output:**
   ```
   1 2 3
   ```
   
   **Reason:** Array destructuring allows you to assign individual elements of the array `num` to the variables `a`, `b`, and `c` in order.

---

### 46. **What will the following code output?**
   ```javascript
   let num = [10, 20, 30];
   let [a, , c] = num;
   console.log(a, c);
   ```

   **Output:**
   ```
   10 30
   ```
   
   **Reason:** The second element (`20`) is skipped using a blank space in the destructuring assignment, so `a` gets `10` and `c` gets `30`.

---

### 47. **What will this code output?**
   ```javascript
   let obj = { name: 'Alice', age: 25 };
   let { name, age } = obj;
   console.log(name, age);
   ```

   **Output:**
   ```
   Alice 25
   ```
   
   **Reason:** Object destructuring extracts the properties `name` and `age` from the `obj` object and assigns them to the respective variables.

---

### 48. **What will the following code output?**
   ```javascript
   let obj = { name: 'Alice', age: 25 };
   let { name: n, age: a } = obj;
   console.log(n, a);
   ```

   **Output:**
   ```
   Alice 25
   ```
   
   **Reason:** The property names are being renamed during destructuring. `name` is assigned to `n` and `age` is assigned to `a`.

---

### 49. **What will the following code output?**
   ```javascript
   const arr = [1, 2, 3];
   const [first, ...rest] = arr;
   console.log(first, rest);
   ```

   **Output:**
   ```
   1 [2, 3]
   ```
   
   **Reason:** The `first` variable gets the first element (`1`), and the `rest` variable gets the remaining elements (`[2, 3]`) as an array using the rest operator.

---

### 50. **What will this code output?**
   ```javascript
   const sum = (a, b) => a + b;
   console.log(sum(5, 3));
   ```

   **Output:**
   ```
   8
   ```
   
   **Reason:** The arrow function `sum` adds the two parameters `a` and `b`, and `5 + 3` results in `8`.

---
