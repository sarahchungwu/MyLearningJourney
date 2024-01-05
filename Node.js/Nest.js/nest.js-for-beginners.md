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

<details>
<summary>2.5 Setting up postgres in docker</summary>


## 2.5 Setting up PostgreSQL in Docker

In this section, we'll guide you through the process of setting up a PostgreSQL database in Docker for your Nest.js application.

### Install Docker

Before you proceed, make sure you have Docker installed on your system. You can download and install Docker from the official website: [Docker Downloads](https://www.docker.com/get-started).

### Configuration of Docker Compose

To set up PostgreSQL in Docker, we'll use Docker Compose. Create a `docker-compose.yml` file with the following configuration:

```yaml
version: '3.8'
services:
  dev-db:
    image: postgres:13
    ports:
      - 5434:5432
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: 123
      POSTGRES_DB: nest
    networks:
      - freecodecamp
  test-db:
    image: postgres:13
    ports:
      - 5435:5432
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: 123
      POSTGRES_DB: nest
    networks:
      - freecodecamp
networks:
  freecodecamp:
```
### In this configuration:

- We define two PostgreSQL services, `dev-db` and `test-db`, each using the PostgreSQL version 13 image.
- Ports `5434:5432` and `5435:5432` are mapped to make the database accessible on those ports.
- Environment variables are set for the PostgreSQL user, password, and database name.
- A network named `freecodecamp` is defined for communication between containers.

### Running Docker Compose

To start the PostgreSQL database in Docker, use the following command:

```bash
docker-compose up dev-db -d
```

This command will start the `dev-db`  service in detached mode `(-d)`, allowing it to run in the background. You can replace `dev-db` with `test-db` if you want to start the test database.

With PostgreSQL running in Docker, you're ready to configure your Nest.js application to connect to this database.


```bash
docker ps
```

The docker ps command is used to list the running Docker containers on your system. When you run this command, it will display a list of containers along with relevant information, such as container IDs, names, status, ports, and more.

```bash
docker logs <containerid>
```
The `docker logs <containerid>` command is used to view the logs generated by a specific Docker container. When you run this command and replace `<containerid>` with the actual ID or name of the container you want to inspect, Docker will display the container's logs in your terminal.

</details>


<details>
<summary>2.6 Setting up prisma</summary>

## 2.6 Setting up prisma

1. Install Prisma and Prisma Client as development dependencies:
```bash
npm install prisma --save-dev

npm i @prisma/client
```
2. Initialize Prisma configuration:
```bash
npx prisma init
```
This command will create the necessary configuration files for Prisma, including the `.env` file with default values. You can then customize the`.env` file variables to match your Docker configuration as needed

This command will also create a Prisma schema file where you can define your database schema.

>Whenever you make changes to the Prisma schema, it's important to run the following command to apply those changes to the database: `npx prisma migrate dev`.
</details>

<details>
<summary>2.7 Defining User and Bookmark Models with Prisma</summary>

  ### 2.7 Defining User and Bookmark Models with Prisma<

  In this section, we'll define the Prisma schema for the User and Bookmark models in the `schema.prisma` file.

  ```prisma
  // This is your Prisma schema file,
  // learn more about it in the docs: [Prisma Schema Docs](https://pris.ly/d/prisma-schema)

  generator client {
    provider = "prisma-client-js"
  }

  datasource db {
    provider = "postgresql"
    url      = env("DATABASE_URL")
  }

  model User {
    id        Int       @id @default(autoincrement())
    createdAt DateTime  @default(now())
    updatedAt DateTime  @updatedAt
    email     String    @unique
    hash      String

    firstName String?
    lastName  String?
    
    bookmarks Bookmark[]
    @@map("users")
  }

  model Bookmark {
    id          Int       @id @default(autoincrement())
    createdAt   DateTime  @default(now())
    updatedAt   DateTime  @updatedAt
    title       String
    description String?
    link        String

    userId      Int
    user        User      @relation(fields: [userId], references: [id])

    @@map("bookmarks")
  }

  ```
  Before we proceed, let's explore some helpful Prisma commands:
  ```bash
  npx prisma --help

  ```
  This command provides a list of commands and options available in Prisma.

  Next, let's run the following command to create an initial migration:

  ```bash
  npx prisma migrate dev
  ```
  When prompted for the name of the migration, you can simply type `init`.

  This sets up the initial database migration for your Prisma schema.

  Then, we will run the following command to generates prisma client code
   ```bash
  npx prisma generate
  ```
  This command generates Prisma client code based on your schema. It creates TypeScript files that allow you to interact with your database using Prisma's strongly typed queries.

  Now, let's clarify the difference between `npx prisma migrate dev` and `npx prisma generate:`

  `npx prisma migrate dev`: This command is used for database migrations. It helps you manage changes to your database schema over time, allowing you to evolve your database structure.

  `npx prisma generate:` This command generates Prisma client code. Prisma client is a type-safe database client that provides a convenient way to interact with your database. It's used for querying and manipulating data in your database.

  >Both commands serve different purposes: one is for database schema evolution (migrations), and the other is for generating code to interact with your database (Prisma client).

</details>

<details>
  <summary> 2.8 Setting Up the Prisma Module</summary>

  ### 2.8 Setting Up the Prisma Module

  In this section, we'll create and configure the Prisma module for our Nest.js application. The Prisma module is essential for connecting and interacting with our database.

  #### Create the Prisma Module

  To create the Prisma module, run the following command:

  - create the service file
  ```bash
  nest g service prisma --no-spec
  ```
  Create the Prisma Service
Next, let's generate the Prisma service, which will provide database access functionality to our application. Use the following command:
  ```bash
  nest g service prisma --no-spec
  ```
This command generates the Prisma service without generating test specifications, keeping our focus on setting up the module and service quickly.

>we'll create a `PrismaService` that allows your Nest.js application to interact with the PostgreSQL database using Prisma.

  First, let's take a look at the code for the `PrismaService`:


```typescript
import { Injectable } from '@nestjs/common';
import { PrismaClient } from '@prisma/client';

@Injectable()
export class PrismaService extends PrismaClient {
  constructor() {
    super({
      // Configure the Prisma client to connect to your PostgreSQL database
      datasources: {
        db: {
          url: 'postgresql://postgres:123@localhost:5434/nest?schema=public',
          // Replace this URL with your actual database connection information
        },
      },
    });
  }
}
```
**Code Breakdown:**

- We create an `Injectable` service called `PrismaService` that extends `PrismaClient` from the `@prisma/client` package. This allows us to use Prisma to interact with the database.

- In the constructor, we configure the Prisma client to connect to your PostgreSQL database. You should replace the `url` property with your actual database connection information.

**Purpose of the PrismaService:**

- The `PrismaService` acts as a central hub for all database-related operations in your Nest.js application. It provides a convenient way to interact with your database using Prisma's strongly typed queries.

- By extending `PrismaClient`, you gain access to various methods and properties that allow you to perform database operations efficiently.

- This service will be used throughout your application to perform CRUD (Create, Read, Update, Delete) operations on your database tables.

With the `PrismaService` set up, you're ready to start building the functionality of your Nest.js application that interacts with the database.

- For the Prisma module
  ```typescript
  import { Global, Module } from '@nestjs/common';
  import { PrismaService } from './prisma.service';

  @Global()
  @Module({
  providers: [PrismaService],
  exports: [PrismaService],
  })
  export class PrismaModule {}
  ```
>With the Prisma module and service set up, you'll have a centralized way to interact with your PostgreSQL database using Prisma's powerful features. This lays the foundation for performing database operations, such as creating, reading, updating, and deleting records, in a structured and efficient manner.

## Integrating Auth Module with Prisma Module

The Auth module in our Nest.js application is tightly integrated with the Prisma module, allowing seamless database operations and user management. Here's how it works:

1. **Import PrismaModule:** In the Auth module, we import the `PrismaModule` to gain access to Prisma's database functionality. This integration enables us to interact with the database effortlessly within our authentication logic.

```typescript
@Module({
  imports: [PrismaModule],
  controllers: [AuthController],
  providers: [AuthService],
})
```
</details>

<details>
<summary>2.9 Using the auth dto</summary>

### 2.9 Using the auth dto

<details>
<summary>The concept of DTO(Data Transfer Object)</summary>

### Concept of DTO (Data Transfer Object)

1. **General Idea**:
   - A DTO is a pattern used to transfer data between software application subsystems. It's essentially a container for data with a defined structure.
   - DTOs are used to encapsulate data and define its format, making data easier to handle, especially when moving between layers (like from the client to the server or between services).

2. **Advantages**:
   - **Structure**: DTOs give a clear structure to the data being passed around.
   - **Type Safety**: In TypeScript, DTOs can enforce types for each property, enhancing code reliability.
   - **Simplification**: They can simplify complex data structures, making them more manageable.
   - **Separation of Concerns**: DTOs help in separating external data presentation from internal data processing.

### Difference When Not Using DTOs

1. **Without DTOs**:
   - You directly handle raw data objects, which might not have a well-defined structure.
   - This can lead to more checks and validations scattered throughout your code, making it less organized.
   - The lack of structure might increase the risk of handling data incorrectly or missing important validations.

2. **Using Validation Libraries (like Zod)**:
   - Libraries like Zod are used for validating data structures. They ensure that the data you receive matches the expected format.
   - Zod focuses on validation, while DTOs focus on data structure and transfer. However, DTOs in TypeScript can also include validation logic (like using `class-validator` in NestJS).

### DTOs in NestJS

1. **Not Compulsory, But Recommended**:
   - Using DTOs in NestJS is not compulsory, but it's a recommended practice.
   - NestJS is designed to work well with DTOs, leveraging TypeScript's type system and decorators.

2. **Benefits in NestJS**:
   - DTOs provide a clear contract for what data a request should contain.
   - They help in automatically handling validation and transformation of incoming data.
   - DTOs enhance maintainability and clarity of your code, making it more aligned with NestJS’s architecture.

### Example Comparison

- **With DTO in NestJS**: You define a class with specific properties and types. When a request comes in, NestJS uses this DTO to ensure the request data matches the expected structure.
- **With Zod in Express.js**: You define a Zod schema for the expected data. When a request is received, you manually validate the request data against this schema.

### Summary

- DTOs are a structural pattern, beneficial for defining the shape and potentially the validation rules of data being transferred.
- They are not mandatory but highly recommended in NestJS due to the framework's design and TypeScript integration.
- Using DTOs leads to cleaner, more maintainable code and aligns well with NestJS's philosophy of structured, modular development. In contrast, while libraries like Zod focus on validation, they don't inherently provide the same level of structural organization as DTOs.
</details>

### Creating the Auth DTO (Data Transfer Object)
In the Auth module, you'll create a DTO file named auth.dto.ts. This DTO will define the structure of data used for authentication.


```typescript
import { IsEmail, IsNotEmpty, IsString } from 'class-validator';

export interface AuthDto {
  email: string;
  password: string;
}
```


Also, export the `AuthDto` in the `index.ts` file within the DTO directory:

```typescript
export * from './auth.dto';
```

This allows you to easily import the `AuthDto` from the `dto` directory in your Nest.js application.


<details>
<summary>Pipes in Nest.js</summary>

### Pipes in Nest.js

## What are Pipes in Nest.js?

Pipes in Nest.js are classes that implement the `PipeTransform` interface. They serve two primary purposes: transformation and validation.

### Transformation:
Pipes are used to modify incoming data into a desired format. For example, they can parse strings into integers or perform other data transformations.

### Validation:
Pipes also play a role in data validation. They check incoming data and can throw exceptions if it doesn't meet specific criteria.

### The Connection: Using Pipes with DTOs
The relationship between DTOs (Data Transfer Objects) and Pipes in Nest.js is mainly centered around the validation and transformation of request data.

#### Automated Validation:
When a client sends data, such as in a POST request, DTOs define the expected data structure. Pipes can automatically validate this data against the DTO's structure and constraints before it reaches the controller's handler method.

**Example Workflow:**

1. A client sends data to a Nest.js API endpoint.
2. The data is received in a controller.
3. Before handling it, a pipe validates (and potentially transforms) this data based on the DTO associated with the endpoint.

#### Built-in Pipes:
Nest.js provides built-in pipes like `ValidationPipe` that seamlessly work with DTOs and class-validator decorators to validate incoming data.

**Example:**

```javascript
import { Controller, Post, Body, UsePipes, ValidationPipe } from '@nestjs/common';
import { CreateItemDto } from './create-item.dto';

@Controller('items')
export class ItemsController {
  @Post()
  @UsePipes(new ValidationPipe())
  async create(@Body() createItemDto: CreateItemDto) {
    // create item logic...
  }
}

```
In this example:

- CreateItemDto defines the structure for creating items.
- ValidationPipe is used to automatically validate data sent to the create method against CreateItemDto.

>For more information, you can refer to the [Nest.js documentation on validation](https://docs.nestjs.com/techniques/validation#stripping-properties).

</details>

### Using the built-in ValidationPipe#
To get started with the `ValidationPipe`, you'll need to install the required dependencies first:

```bash
$ npm i --save class-validator class-transformer
```
Next, let's make some changes to your `auth.dto.ts` file to include validation decorators:

```typescript
import { IsEmail, IsNotEmpty, IsString } from 'class-validator';

export class AuthDto {
  @IsEmail()
  @IsNotEmpty()
  email: string;

  @IsString()
  @IsNotEmpty()
  password: string;
}
```

Now, let's integrate the `ValidationPipe` into your `main.ts` file to apply validation globally:


```typescript
 import { ValidationPipe } from '@nestjs/common';

// ...

async function bootstrap() {
  const app = await NestFactory.create(AppModule);

  // Apply ValidationPipe globally
  app.useGlobalPipes(
    new ValidationPipe({
      whitelist: true,
    }),
  );

  await app.listen(3000);
}
bootstrap();

```

> With these changes, your Nest.js application will use the `ValidationPipe` to automatically validate incoming data against the defined DTO structure. `The whitelist: true` option ensures that only properties with decorators are allowed, stripping any additional properties.


</details>

<details>
<summary> 2.10 Hashing user password with argon</summary>

### 2.10 Hashing user password with argon

**Step 1**: Install the Argon2 library by running the following command:
```bash
npm i argon2
```

**Step 2**: Create the signup logic in your Nest.js AuthService. Here's the code:
```typescript
import { ForbiddenException, Injectable } from '@nestjs/common';
import { PrismaService } from 'src/prisma/prisma.service';
import { AuthDto } from './dto';
import * as argon2 from 'argon2';
import { PrismaClientKnownRequestError } from '@prisma/client/runtime/library';

@Injectable()
export class AuthService {
  constructor(private prisma: PrismaService) {}

  async signup(dto: AuthDto) {
    try {
      // Generate the password hash using Argon2
      const hash = await argon2.hash(dto.password);

      // Save the new user in the database
      const user = await this.prisma.user.create({
        data: {
          email: dto.email,
          hash,
        },
      });

      // Remove the hash from the returned user object for security
      delete user.hash;

      // Return the saved user
      return user;
    } catch (error) {
      // Handle any errors, including duplicate credentials
      if (error instanceof PrismaClientKnownRequestError) {
        if (error.code === 'P2002') {
          throw new ForbiddenException('Credentials already taken');
        }
      }
      throw error;
    }
  }
}

```
This code demonstrates how to securely hash user passwords using Argon2 and handle exceptions, such as duplicate credentials. The argon2.hash function is used to hash the user's password before storing it in the database.

By following these steps, you can ensure that user passwords are stored securely in your Nest.js application.


</details>