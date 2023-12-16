
# Introduction to  JavaScript

### What is JavaScript ?

JavaScript is a cross-platform, object-oriented scripting language used to make webpages interactive (e.g., having complex animations, clickable buttons, popup menus, etc.).

JavaScript contains a standard library of objects, such as Array, Date, and Math, and a core set of language elements such as operators, control structures, and statements. Core JavaScript can be extended for a variety of purposes by supplementing it with additional objects; for example:

- Client-side JavaScript extends the core language by supplying objects to control a browser and its Document Object Model (DOM). For example, client-side extensions allow an application to place elements on an HTML form and respond to user events such as mouse clicks, form input, and page navigation.
- Server-side JavaScript extends the core language by supplying objects relevant to running JavaScript on a server. For example, server-side extensions allow an application to communicate with a database, provide continuity of information from one invocation to another of the application, or perform file manipulations on a server.
- This means that in the browser, JavaScript can change the way the webpage (DOM) looks. And, likewise, Node.js JavaScript on the server can respond to custom requests sent by code executed in the browser.

### Java vs JavaScript

JavaScript and Java are similar in some ways but fundamentally different in some others. The JavaScript language resembles Java but does not have Java's static typing and strong type checking. JavaScript follows most Java expression syntax, naming conventions and basic control-flow constructs which was the reason why it was renamed from **LiveScript to JavaScript**.

**Comparison of JavaScript and Java**

| Feature | JavaScript | Java |
|---|---|---|
| Object Model | Object-oriented, no type distinction | Class-based, inheritance through hierarchy |
| Inheritance | Prototype mechanism, dynamic additions | Class hierarchy, static additions |
| Typing | Dynamic, no type declaration | Static, strong typing with declaration |
| File System Access | No automatic write access | Automatic write access to hard disk |

### JavaScript and the ECMAScript specification

JavaScript is standardized at Ecma International — the European association for standardizing information and communication systems (ECMA was formerly an acronym for the European Computer Manufacturers Association) to deliver a standardized, international programming language based on JavaScript. This standardized version of JavaScript, called ECMAScript, behaves the same way in all applications that support the standard. Companies can use the open standard language to develop their implementation of JavaScript. The ECMAScript standard is documented in the ECMA-262 specification.

**Breakdown of the above** -

**Cross platform** - meaning you can write the same code and run it on various platforms without major modifications.

- Web Development - Imagine you create a website with interactive features like animations or user input forms. You write the code in JavaScript, and all modern web browsers can understand and execute it, regardless of the operating system (Windows, macOS, Linux, etc.).

- Mobile App Development - Frameworks like React Native and Ionic allow you to write JavaScript code that compiles into native mobile apps for Android and iOS. This means you can build a single codebase for both platforms, saving time and resources.

- Server-Side Scripting - Node.js is a popular runtime environment that lets you run JavaScript code on the server-side. This opens up possibilities for building web applications, APIs, and even command-line tools.

**Object Oriented Scripting** -

- What is Object-Oriented Programming (OOP) ? -
  - OOP organizes code around objects, which represent real-world entities like users, products, or devices.
  - Objects contain data (properties) and code (methods) that manipulate that data.
  - OOP principles like encapsulation, inheritance, and polymorphism promote modularity, reusability, and maintainability of code.

- What are Scripting Languages ? -
  - Scripting languages are designed for rapid development and automation.
  - They often have simpler syntax and fewer formalities than traditional compiled languages.
  - Scripts are often interpreted directly, allowing for quick testing and execution.

- Combining these two concepts
  - Object-oriented scripting languages let you leverage the benefits of OOP within the ease and flexibility of scripting.
  - You can build modular, reusable programs with objects while enjoying the rapid development and dynamic execution of scripting languages.

- Examples - JS, Python and Ruby

- Benefits of Object-Oriented Scripting Languages

  - Improved code organization and structure: Objects group related data and functionality, making code easier to understand and maintain.
  - Increased code reusability: Inheritance allows you to share code between related objects, reducing redundancy and saving time.
  - More flexible and dynamic programs: OOP principles like polymorphism enable flexible and adaptable code that can handle diverse situations.
  - Faster development and prototyping: Scripting languages facilitate rapid testing and iteration, making development more efficient.

**DOM** - The DOM (Document Object Model) is like a map of a website, but for programmers. It represents the structure and content of a web page as a hierarchy of objects, making it easier for programming languages like JavaScript to interact with and modify the page.

 Imagine a website as a tree:

The document object is the root.

- Branches are major sections like header, body, and footer.
- Leaves are individual elements like paragraphs, images, and buttons.
- Each element has properties (like text content, style, and attributes) and methods (like hiding, showing, or changing).
- By manipulating these objects, developers can create dynamic and interactive web experiences.

 Benefits of DOM:

- Dynamically update web pages: Change text, hide elements, add animations, and more.
- Build interactive features: Implement forms, menus, and user feedback mechanisms.
- Access and manipulate data: Read and modify content from the page or other sources.
- Standardized interface: Works across different browsers and programming languages.
