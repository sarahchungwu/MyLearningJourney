## Section 1: Introduction to Nest.js
<details>
  <summary>What is Nest.js</summary>

# What is Nest.js?

Nest.js is a progressive Node.js framework for building efficient and scalable server-side applications. It is built on top of Express (by default) and uses TypeScript. Nest.js provides a level of abstraction above these common Node.js frameworks but also exposes their APIs to the developer. This allows for easy use of the myriad third-party modules available for each platform.


</details>

<details>
  <summary>Why use Nest.js</summary>

# Why Use Nest.js?

Nest.js offers several advantages making it a compelling choice for server-side development:

## Structure
Nest.js provides a clear and well-defined structure right from the start. This structure helps in organizing the application and makes it more maintainable in the long run.

## Modularity
The framework emphasizes modularity, allowing developers to break down their application into different modules. This makes the codebase more manageable and scalable.

## TypeScript
Nest.js is built with TypeScript support and encourages its use, although it still enables developers to write in pure JavaScript. TypeScript provides strong typing and object-oriented programming features, leading to more robust and error-free code.

## GraphQL Integration
Nest.js has excellent support for GraphQL, a powerful query language for APIs, and provides a straightforward way of building efficient and scalable APIs.

## Microservices
It is well-suited for building microservice architectures, offering various tools and features to handle inter-service communication effectively.

## RESTful API Development
Nest.js is a great choice for building RESTful APIs with its rich set of decorators and modules, simplifying the handling of HTTP requests and responses.

## Easy Documentation
With tools like Swagger, Nest.js makes it easy to document your APIs, which is essential for large-scale applications and teams.

## Popularity
Nest.js has been gaining popularity rapidly in the Node.js community due to its robust architecture and the convenience it offers. This popularity has led to a growing community and ecosystem, providing support and resources for developers.

</details>

<details>
  <summary>NestJs project setup</summary>

# NestJs project setup?

### installation
```shell
$ npm i -g @nestjs/cli
$ nest new project-name
```


</details>

<details>
  <summary>Modules</summary>

# What is Module?
[Link to Nest.js Modules Documentation](https://docs.nestjs.com/modules)

<details>
  <summary>Concept Module</summary>
  
 
  ### Key Points about Nest.js Modules:

- **Organization**: Modules are the primary way of organizing controllers, services, and other elements in Nest.js. Each module is a class decorated with `@Module()`.

- **Encapsulation**: They encapsulate providers (like services) and controllers, ensuring a clear and structured architecture. This means that everything that is related to a specific feature or functionality is bundled together.

- **Reusability**: You can easily reuse a module in different parts of your application, just like how you might reuse a set of tools for different projects.

- **Modularity**: This concept promotes a modular architecture, encouraging you to divide your application into distinct features with their boundaries. It's like building a Lego structure, where each block (or module) has its specific place and purpose.

- **Structure**: A typical module might include components like controllers to handle incoming requests, providers for business logic, and imports of other modules if needed.

### Example:

Here's a simple example of a Nest.js module:

```typescript
  import { Module } from '@nestjs/common';
  import { YourService } from './your.service';
  import { YourController } from './your.controller';

  @Module({
    imports: [],
    controllers: [YourController],
    providers: [YourService],
  })
  export class YourModule {}
```
In this example:

- `@Module()` is a decorator indicating that `YourModule` is a Nest.js module.

- Inside the `@Module()` decorator, `controllers` and `providers` are specified, which themselves are classes decorated with `@Controller()` and `@Injectable()` respectively.

## What is a Decorator?

A decorator in programming, particularly in Nest.js and other TypeScript-based frameworks, is a special kind of declaration that can be attached to a class declaration, method, accessor, property, or parameter. Decorators use the form `@expression`, where `expression` must evaluate to a function that will be called at runtime with information about the decorated declaration.

### Key Points about Decorators:

- **Metadata Attachment**: Decorators are a way to add metadata to your class, method, etc. This metadata can then be used to modify the behavior of your code at runtime.
  

  <details>
    <summary>Explain what is the metadata</summary>

    ## Understanding Metadata in Programming

  Metadata, in the context of programming and particularly in frameworks like Nest.js, refers to data that provides information about other data. It's akin to a set of instructions or details that describes the characteristics, properties, or features of your code elements. This concept is crucial in comprehending how decorators work in Nest.js and other TypeScript-based frameworks.

  ### Exploring Metadata in Programming:

  - **Description of Data**: Metadata is essentially data about data. To illustrate, consider a library where metadata about a book includes details like its title, author, publication date, and genre. In programming, metadata describes aspects such as the behavior of classes, methods, or properties.

  - **Role in Decorators**: In Nest.js, decorators leverage metadata to augment classes, methods, or properties with additional information. This information guides the framework in determining how to treat those elements. For instance, a decorator might inform Nest.js that a particular class functions as a controller and should handle HTTP requests.

  - **Runtime Influence**: Metadata can influence how your code behaves during runtime. The framework reads the metadata and takes specific actions based on it. For instance, metadata can dictate how dependency injection is managed or how routing is configured in a web application.

  - **Reflection**: TypeScript and Nest.js often utilize a feature called reflection to access and utilize metadata. Reflection is a programming mechanism that allows inspection and modification of the structure and behavior of your program at runtime.

  ### Example in Nest.js:

  Let's consider a simple controller in Nest.js:

  ```typescript
  import { Controller, Get } from '@nestjs/common';

  @Controller('users')
  export class UsersController {
    @Get()
    findAll() {
      //...
    }
  }
  ```
  Here's how metadata is applied in this scenario:

  - `@Controller('users')`: This decorator is used to associate metadata with the `UsersController` class, indicating that it serves as a controller for handling HTTP requests directed at the `/users` endpoint.

  - `@Get()`: This decorator is employed to associate metadata with the `findAll` method, explicitly specifying that it's intended to handle GET requests.

  </details>




- **Declarative Programming**: Decorators allow for a more declarative style of programming. Instead of explicitly writing code to handle certain behaviors, you can use decorators to manage this for you.

- **Common Uses in Nest.js**: In Nest.js, decorators are used for routing, dependency injection, module declaration, etc.

### Relationship between Decorators and Modules in Nest.js

In Nest.js, modules and decorators are closely related and work together to provide structure and functionality to your application.

- **Modules as Decorators**: The `@Module()` decorator is used to define a module. This decorator takes an object that can have properties like providers, controllers, imports, and exports. These properties tell Nest.js how to assemble the application.

- **Structural Organization**: Modules use decorators not just for their own definition, but also to organize other parts of the application. For example, controllers and services within a module use decorators like `@Controller()` and `@Injectable()` to declare their role within the module.

- **Dependency Injection**: The decorators in Nest.js, particularly within modules, facilitate dependency injection. This allows for loosely coupled design, enhancing modularity and maintainability of the application.

</details>
</details>



## Section 2: Project Development

In this section, we will explore the key commands and tools that you'll use for developing your Nest.js project.

<details>
  <summary>2.1. Starting the Development Server</summary>

### 2.1. Starting the Development Server

To kickstart your project development, you'll need to start the development server. The following command will be your go-to:

```bash
npm run start:dev
```

Running `npm run start:dev` will launch your Nest.js application in development mode, enabling features like hot-reloading for rapid development. This command is crucial for a smooth development workflow.

</details>


<details>
  <summary>2.2. Generating Modules with Nest CLI</summary>

### 2.2. Generating Modules with Nest CLI

[Nest CLI](https://docs.nestjs.com/cli/overview) (Command Line Interface) is a powerful tool for scaffolding various parts of your Nest.js application. One of the fundamental tasks in building your application is creating modules.

To generate a module, use the following Nest CLI command:

```bash
nest g module user
```
This command creates a new module named "user" with all the necessary files and boilerplate code. Modules are a fundamental concept in Nest.js for organizing your application into logical units, and this command helps you get started quickly.

### We will using `nest g module user` &  `nest g module bookmark` to create user and bookmark module

</details>

<details>
  <summary>2.3 Application Module -AppModule </summary>

### 2.3 Application Module (`AppModule`)

The `AppModule` is the main module of your Nest.js application. It defines the modules that your application depends on.

```typescript
import { Module } from '@nestjs/common';
import { AuthModule } from './auth/auth.module';
import { UserModule } from './user/user.module';
import { BookmarkModule } from './bookmark/bookmark.module';
import { PrismaModule } from './prisma/prisma.module';

@Module({
  imports: [AuthModule, UserModule, BookmarkModule, PrismaModule],
})
export class AppModule {}
```
**2.3.1 Auth Module (AuthModule)**
The AuthModule provides authentication-related features for your application.

**2.3.2 User Module (UserModule)**
The UserModule is responsible for managing user-related functionalities.

**2.3.3 Bookmark Module (BookmarkModule)**
The BookmarkModule handles bookmark-related operations in your application.

</details>

<details>
<summary>2.4 Auth Module</summary>

### 2.4 Auth Module

<details>
  <summary>The concept of Dependency Injection  </summary>

  ## What is Dependency Injection?

Dependency Injection (DI) is a design pattern used in software development to achieve Inversion of Control (IoC) between classes and their dependencies. Here's a simple way to understand it:

Imagine you're building a robot. Instead of hard-wiring all its parts, you design it so that you can plug in different components (like a battery, sensors, etc.). This makes your robot flexible and easier to upgrade or repair.

In programming, DI allows you to "inject" objects into a class, rather than having the class create the object itself. This makes your code more modular, testable, and maintainable.

### How Dependency Injection Works in Nest.js:

**Providers**: In Nest.js, services (also known as providers) are often the dependencies that get injected. These are classes annotated with the `@Injectable()` decorator.

**Injecting Providers**: When a class (like a controller) needs a service, Nest.js injects an instance of the service into the class. The controller doesn't need to know where the service comes from or how it's created.

**Modules and Providers**: The `@Module()` decorator is used to organize providers. It tells Nest.js which providers are available for injection and how they should be scoped.

### Example:

Here's a basic example of how dependency injection works in Nest.js:

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class YourService {
  doSomething(): string {
    return "Doing something!";
  }
}

import { Controller, Get } from '@nestjs/common';
import { YourService } from './your.service';

@Controller()
export class YourController {
  constructor(private yourService: YourService) {}

  @Get()
  getSomething(): string {
    return this.yourService.doSomething();
  }
}
```
### In this example:

- `YourService` is a provider (service).
- `YourController` is a consumer of `YourService`.
- Nest.js automatically injects an instance of `YourService` into `YourController` through the constructor. The controller can then use the service's methods.

### Benefits of Dependency Injection:

- **Loose Coupling**: Your classes don't depend on specific implementations of their dependencies, making them more flexible.

- **Easier Testing**: You can easily replace real services with mock objects in tests.

- **Modularity**: It encourages a modular structure, where different parts of your application can be developed and maintained independently.


</details>

### AuthService

```typescript
 import { Injectable } from '@nestjs/common';


@Injectable()
export class AuthService {
 signup(){
  return {msg: 'I have signed up'}
 }

 signin(){
  return {msg: 'I have signed in'}
 }

}

```

### AuthController

```typescript
import { Controller, Post } from '@nestjs/common';
import { AuthService } from './auth.service';

@Controller('auth')
export class AuthController {
  constructor(private authService: AuthService) {}

  @Post('signup')
  signup() {
    return this.authService.signup();
  }

  @Post('signin')
  signin() {
    return this.authService.signin();
  }
}

```

### AuthModule

```typescript
import { Module } from '@nestjs/common';
import { AuthController } from './auth.controller';
import { AuthService } from './auth.service';

@Module({
  controllers: [AuthController],
  providers: [AuthService],
})
export class AuthModule {}


```


</details>
