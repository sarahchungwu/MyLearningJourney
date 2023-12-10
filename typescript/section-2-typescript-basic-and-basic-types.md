
# Section 2 - Typescript Basic & Basic Types

## TypeScript vs. JavaScript


<details>
  <summary> Explain the Difference</summary>

  ### 1. **Type System**

- **JavaScript**: It's a dynamically typed language. This means that variable types are determined at runtime and can change. For example, a variable initially holding a number can later be assigned a string.
- **TypeScript**: A statically typed language, where you specify types for variables, function parameters, and return values at compile time. This helps in catching type-related errors early in the development process.

### 2. **Compilation**

- **JavaScript**: It's an interpreted language and doesn't need a compilation step. Browsers can run JavaScript directly.
- **TypeScript**: Requires a compilation step, where TypeScript code is transpiled to JavaScript. This is because browsers can't execute TypeScript directly.

### 3. **Error Checking**

- **JavaScript**: Most errors are found at runtime, which can be later in the development process.
- **TypeScript**: Offers advanced error checking features. Many errors, especially those related to types, are caught at compile time.

### 4. **Tooling and Development Experience**

- **TypeScript**: Provides enhanced development experience with better tooling. Features like auto-completion, interface checking, and refactoring tools are more robust due to the static type system.
- **JavaScript**: Tooling is improving, but it's inherently limited by the language's dynamic nature.

### 5. **Learning Curve**

- **JavaScript**: More straightforward for beginners due to its dynamic nature and wide usage in web development.
- **TypeScript**: Has a steeper learning curve if you're not familiar with static type systems, but it's generally easy to pick up for those with JavaScript experience.

### 6. **Community and Ecosystem**

- **JavaScript**: Has a vast and established community with a plethora of resources, libraries, and frameworks.
- **TypeScript**: Rapidly growing in popularity, especially in larger projects or where code maintainability is a priority. Most major JavaScript libraries and frameworks now offer TypeScript support.

### 7. **Use Cases**

- **JavaScript**: Suitable for a wide range of applications, from small scripts to large web applications.
- **TypeScript**: Particularly beneficial in larger projects, projects with multiple developers, or projects that require a high level of maintainability.

### 8. **Superset/Subset Relationship**

- **TypeScript** is a superset of JavaScript, meaning any valid JavaScript code is also valid TypeScript code. TypeScript adds additional features on top of JavaScript, primarily related to the type system.

In summary, TypeScript enhances JavaScript with types and provides better tooling support, which can lead to more robust and maintainable codebases, especially in larger projects. However, it requires a compilation step and has a slightly steeper learning curve. Your JavaScript skills are directly transferable to TypeScript, making it a valuable addition to your skillset as a developer.

</details>




## Working with Numbers, Strings & Booleans
TypeScript enhances JavaScript's basic types - numbers, strings, and booleans - with static typing. Here's a brief overview of how these types are used in TypeScript.
<details>
  <summary>Numbers</summary>

  ## Numbers
> In TypeScript, numbers can be of type `number`. This includes both integers and floating-point numbers.

```typescript
let integer: number = 6;
let float: number = 3.14;
```
</details>

<details>
  <summary>Strings</summary>

  ##Strings
> String values in TypeScript are similar to JavaScript and are defined using the string type.

```typescript
let greeting: string = "Hello, TypeScript!";
```
</details>

<details>
  <summary>Booleans</summary>

  ##Booleans
Boolean values are simple true/false values in TypeScript, denoted by the boolean type.

```typescript
let isComplete: boolean = false;
```
</details>




## Type Assignment and Type Inference in TypeScript

> In TypeScript, you have two fundamental ways to specify data types for variables, function parameters, and return values: **Type Assignment** and **Type Inference**.

### Type Assignment

<details>
  <summary>Type Assignment</summary>


**Type Assignment** involves explicitly specifying the data type when you declare a variable or define function parameters and return values. Here's how it works:

```typescript
// Explicitly assigning types to variables
let age: number = 30; // 'age' is of type 'number'
let name: string = "Alice"; // 'name' is of type 'string'
let isStudent: boolean = true; // 'isStudent' is of type 'boolean'

// Explicitly assigning types to function parameters and return values
function add(x: number, y: number): number {
  return x + y;
}
```
Type assignment provides clarity about the expected data type of a variable, parameter, or return value, and it helps catch type-related errors early in development.

</details>

### Type Inference
<details>
  <summary>Type Inference</summary>


**Type Inference** is a feature of TypeScript that allows the compiler to automatically deduce the data type based on initialization values or usage. Here's how type inference works::

```typescript
// Explicitly assigning types to variables
// Type inference based on initialization value
let age = 30; // TypeScript infers 'age' as type 'number'
let name = "Bob"; // TypeScript infers 'name' as type 'string'

// Type inference in function parameters and return values
function multiply(x: number, y: number) {
  return x * y; // TypeScript infers the return type as 'number'
}

```
With type inference, you don't need to explicitly specify types, making your code more concise while still maintaining type safety. TypeScript automatically deduces types based on context, which is especially helpful when dealing with complex data structures and function return values.
</details>




>In summary, type assignment  involves explicitly specifying data types, providing clarity and early error checking. Type inference, on the other hand, lets TypeScript automatically deduce types based on context, reducing the need for explicit type annotations and improving code conciseness. Both mechanisms work together to enhance TypeScript's strong typing capabilities.



---
