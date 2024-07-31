# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json', './tsconfig.app.json'],
    tsconfigRootDir: __dirname,
  },
}
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list

# TypeScript Basics and Concepts

## Basic Types

### Number
In TypeScript, `number` is used to define variables that hold numeric values.

```typescript
let age: number = 25;
```

### String

The string type is used to define variables that hold textual data.

```typescript
let name: string = "Hardik";
```

### Boolean

The boolean type is used to define variables that hold true or false values.

```typescript
let isDeveloper: boolean = true;
```

### Array

An array in TypeScript can be defined to hold elements of a specific type.

```typescript
An array in TypeScript can be defined to hold elements of a specific type.
```

### Tuple

Tuples allow you to express an array with a fixed number of elements whose types are known.

```typescript
let user: [string, number] = ["Hardik", 25];
```

### Enum

Enums allow a developer to define a set of named constants. TypeScript provides both numeric and string-based enums.

```typescript
enum Color {
  Red,
  Green,
  Blue
}
let c: Color = Color.Green;
```

### Any

The any type allows a variable to hold values of any type, essentially opting out of type checking.

```typescript
let something: any = "Hello";
something = 42;
```

### Void 
`void` is used to indicate that a function does not return any value. 

```typescript
function logMessage(message: string): void { console.log(message); }
```

### Null and Undefined
null and undefined are subtypes of all other types and can be assigned to any type.

```typescript
let u: undefined = undefined;
let n: null = null;
```

### Never
The never type represents the type of values that never occur. For example, a function that always throws an exception or one that never returns.

```typescript
  function error(message: string): never {
  throw new Error(message);
}

```

## Advanced Types

### Object
The object type represents non-primitive types.

```typescript
let person: { name: string; age: number } = {
  name: "Hardik",
  age: 25,
};

```

### Type Alias
Type aliases create a new name for a type. They are useful for simplifying complex type definitions.

```typescript
type Point = {
  x: number;
  y: number;
};
let point: Point = { x: 10, y: 20 };
```

### Interface
Interfaces define the structure of an object and can be implemented by classes or used to type-check an object.


```typescript
interface Person {
  name: string;
  age: number;
}
let person: Person = {
  name: "Hardik",
  age: 25,
};

```

### Union Types
Union types allow a variable to hold values of multiple types.

```typescript
let id: number | string;
id = 10;
id = "10";
```

### Intersection Types
Intersection types combine multiple types into one. This is useful when you want to merge properties from different types into a single type.

```typescript
type Drivable = {
  drive(): void;
};

type Flyable = {
  fly(): void;
};

type Vehicle = Drivable & Flyable;

let carPlane: Vehicle = {
  drive: () => console.log("Driving"),
  fly: () => console.log("Flying")
};

```

### Extending Interfaces
Interfaces can be extended to create new interfaces with additional properties. This is useful for creating hierarchies and reusing common properties.

```typescript
interface Animal {
  name: string;
}

interface Dog extends Animal {
  breed: string;
}

let myDog: Dog = {
  name: "Buddy",
  breed: "Golden Retriever"
};

```

### Generics
Generics provide a way to create reusable components that can work with a variety of types.

```typescript
function identity<T>(arg: T): T {
  return arg;
}
let output = identity<string>("myString");

```

## Type Utilities


### `typeof` Operator (Runtime)
The typeof operator returns a string indicating the type of the unevaluated operand.

```typescript
let age: number = 25;
console.log(typeof age); // "number"

let name: string = "Hardik";
console.log(typeof name); // "string"

```

### `keyof` Operator
The keyof operator takes an object type and produces a string or numeric literal union of its keys.

```typescript
interface Person {
  name: string;
  age: number;
}

type PersonKeys = keyof Person; // "name" | "age"

```

### `typeof` Type Query
The typeof type query operator is used to obtain the type of a variable or object.

```typescript
let person = {
  name: "Hardik",
  age: 25,
};

type PersonType = typeof person;
// PersonType is { name: string; age: number; }

```

### `instanceof` Operator
The instanceof operator checks whether an object is an instance of a specific class.

```typescript
class Car {
  model: string;
  constructor(model: string) {
    this.model = model;
  }
}

let myCar = new Car("Toyota");

console.log(myCar instanceof Car); // true

```


