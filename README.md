# JavaScript Objects

## 1. Basics of Objects
The Object type represents one of JavaScript's data types. It is used to store various keyed collections and more complex entities. Objects can be created using the Object() constructor or the object initializer / literal syntax.

```js
let person = {
  name: "John",
  age: 30,
  isStudent: false
};
```

### Activity:
Create an object `car` with properties `brand`, `model`, and `year`. Log the object to the console.

## 2. Referencing and Copying
Objects are **reference types**. When you assign or pass an object, you're copying the reference, not the actual object.

```js
let original = { name: "Alice" };
let copy = original;
copy.name = "Bob";
console.log(original.name); // Output: Bob (because `copy` and `original` refer to the same object)
```

### Activity:
Create an object `book`, then create a copy and modify a property. Observe the changes in both.

## 3. Object Methods and the `this` Keyword
Objects can have **methods** (functions as properties). The `this` keyword refers to the object calling the method.

```js
let calculator = {
  value: 10,
  add(num) {
    return this.value + num;
  }
};

console.log(calculator.add(5)); // Output: 15
```

### Activity:
Create an object `counter` with a method `increment` that increases a `count` property by 1 each time it's called.

## 4. Constructor Functions and the `new` Operator
Constructor functions allow you to create multiple objects of the same type.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

let user = new Person("Emma", 25);
console.log(user.name); // Output: Emma
```

### Activity:
Create a constructor function `Animal` that takes `species` and `sound` as arguments and logs the sound.

## 5. Optional Chaining (`?.`)
Optional chaining allows you to safely access deeply nested properties without worrying about `null` or `undefined`.

```js
let user = { address: { city: "New York" } };
console.log(user?.address?.city); // Output: New York
console.log(user?.contact?.phone); // Output: undefined
```

### Activity:
Create an object `student` with nested properties and use optional chaining to access them.

## 6. Symbol Type and Object to Primitive Conversion
**Symbols** are unique identifiers for object properties.

```js
let id = Symbol("id");
let user = { [id]: 123 };
console.log(user[id]); // Output: 123
```

When converting objects to primitives, JavaScript uses `toString` or `valueOf`.

```js
let user = {
  name: "Jane",
  toString() {
    return this.name;
  }
};

console.log(String(user)); // Output: Jane
```

### Activity:
Create an object and override the `toString` method to return a custom message.

## 7. Object Properties Configuration
Every property in an object has associated flags and descriptors like `writable`, `enumerable`, and `configurable`.

```js
let user = {};
Object.defineProperty(user, "name", {
  value: "John",
  writable: false
});

user.name = "Alice"; // Error (because writable is false)
```

### Activity:
Create an object and use `Object.defineProperty` to add a read-only property.

## 8. Flags (Writable, Enumerable, Configurable) and Descriptors
These flags control how properties behave in objects:
- **writable**: Can the value be changed?
- **enumerable**: Will the property appear in `for..in` loops?
- **configurable**: Can the property be deleted or modified?

```js
let person = {};
Object.defineProperty(person, "age", {
  value: 25,
  writable: true,
  enumerable: false,
  configurable: true
});
```

### Activity:
Create an object with non-enumerable properties. Use a `for...in` loop to verify the properties.

## 9. Property Getters and Setters
Getters and setters allow you to define computed properties in objects.

```js
let user = {
  firstName: "John",
  lastName: "Doe",
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },
  set fullName(value) {
    [this.firstName, this.lastName] = value.split(" ");
  }
};

user.fullName = "Jane Smith";
console.log(user.firstName); // Output: Jane
```

### Activity:
Create an object with `getter` and `setter` methods for a full name and test it.
```

This note covers key concepts of JavaScript objects, offering interactive activities to solidify learning. Let me know if you want any changes or additions!
