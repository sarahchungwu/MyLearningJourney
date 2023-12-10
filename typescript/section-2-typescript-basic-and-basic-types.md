
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


---

## Working with Numbers, Strings & Booleans
TypeScript enhances JavaScript's basic types - numbers, strings, and booleans - with static typing. Here's a brief overview of how these types are used in TypeScript.
<details>
  <summary>Numbers</summary>

  ## Numbers
In TypeScript, numbers can be of type `number`. This includes both integers and floating-point numbers.

```typescript
let integer: number = 6;
let float: number = 3.14;
```
</details>

<details>
  <summary>Strings</summary>

  ##Strings
String values in TypeScript are similar to JavaScript and are defined using the string type.

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

### Type Inference
TypeScript is also capable of inferring these types if you assign a value at declaration.
```typescript
let inferredNumber = 5; // number
let inferredString = "Inferred String"; // string
let inferredBoolean = true; // boolean

```
Remember, while these basic types are straightforward, they form the building blocks for more complex structures and types in TypeScript.

---
