###### *This article is sponsored by [Flutterwave](https://dashboard.flutterwave.com/signup?referrals=RV686851) - Flutterwave is the easiest way to make and accept payments both online and offline from customers anywhere in the world. It is absolutely free!*

---
**React** happens to be the most popular JavaScript framework sourced from [Stack Overflow Developer Survey](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks-wanted2) (2020). It is the best alternative to two other popular JavaScript frameworks, [Angular](https://angular.io/) and [Vue](https://vuejs.org/). They all allow you to create fast apps in the browser.

According to the [official React website](https://reactjs.org/):
> React is a JavaScript library for building user interfaces

In the definition above, the term *user interface* is also called a component to React.

A **template-like component** can be created for reuse in a single web app. It totally adheres to the **Don't Repeat Yourself** (**DRY**) principle. 

You only have to change the data in the components. These feature in JavaScript makes it easier to write shorter code for complex applications.

---
### What are the components?
A simple definition of components is:
> Components are independent and reusable bits of code

They serve the same purpose as JavaScript functions but work in isolation and return **HTML** (*index.html*) via a render function.

Components come in three types:
1. Class components
2. Function components
3. Server Components

We will see functional components usage here!

The image below [shows part of the official React home page](https://reactjs.org/) divided into components:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/1skjueuuny3fzcyq38tu.jpg)

Let's take a look at the latter components (the bottom 3 components). It shows a component reusable in a web app.

---
### How to build components in React?
Let's use [Codepen](https://codepen.io/) to illustrate.

Steps: 
- Click the Signup button and signup (optional).
- Click the Start Coding button.
- Click the gear icon for setting to React.
- Give a title of your project in the Pen Title field (optional).
- Description of your project in the Pen Description field (optional).
- Tag your project in the Tags field (Optional).
- Select JS in the sidebar.
- Select Babel in the JavaScript Preprocessor dropdown.
- Search the following in the CDNjs search field.
 - react (select and click).
 - react-dom (select and click).
- Click the Save and Close button.

In normal **HTML** and **CSS**, the code source of the bottom three components is shown below:

**HTML**
```html
<section>
  <div class='component-1 component'>
    <h3>Declarative</h3>
    <p>React makes it painless to create interactive UIs...</p>
    <p>Declarative views make your code more predictable...</p>
  </div>

  <div class='component-2 component'>
    <h3>Component-Based</h3>
    <p>Build encapsulated components that manage their...</p>
    <p>Since component logic is written in JavaScript...</p>
  </div>

  <div class='component-3 component'>
    <h3>Learn Once, Write Anywhere</h3>
    <p>We don't make assumptions about the rest of...</p>
    <p>React can also render on the server using...</p>
  </div>
</section>
```

**CSS**
```css
section {
  display: flex;
  flex: 0 1 30%;
  -webkit-flex: 0 1 30%;
  margin: 0 auto;
  width: 97%;
  overflow-x: auto;
}

.component {
  margin-left: 5px;
  margin-right: 5px;
  padding: 10px
}

h3 {
  font-size: 1.25rem;
  font-family: sans-serif;
  margin-bottom: 20px;
  color: #6d6d6d;
  padding-top: 0;
  font-weight: 300;
  line-height: 1.3;
}

p {
  margin-top: 0;
  font-size: 1.0625rem;
  line-height: 1.7;
  max-width: 42rem;
}

a {
  background: #bbeffdad;
  background-color: #bbeffdad;
  color: #1a1a1a;
  border-bottom: 1px solid #00000033;
  text-decoration: none;
}

h3,
p {
  font-family: sans-serif;
}

a:hover {
  background: #bbeffd;
  background-color: #bbeffd;
}

@media (max-width: 779px) {
  .component {
    min-width: 50%;
    margin-left: 0;
    margin-right: 0;
  }
}

@media (max-width: 600px) {
  .component {
    min-width: 80%;
    margin-left: 0;
    margin-right: 0;
  }
}
```

#### Template-like Component
In the example shown below, a template-like component, `Adcomponent` is created:

- A react component in its most basic form is just a function (functional component). React supports ES6+ syntax, like the **fat arrow function**.

```jsx
const Adcomponent = props => {...}
```

- Components with more than one React element are placed in a parent element. The parent element here is the `<div>` element

**JSX**
```jsx
<div className="component-1 component">
    <h3>{props.adHeading}</h3>
    <p>{props.adParagraph1}</p>
    <p>{props.adParagraph2}</p>
</div>
```

- Place all hierarchy React elements in parenthesis to return them to the **DOM** (**Document Object Model**) successfully. 

```jsx
return (
    <div className="component-1 component">
      <h3>{props.adHeading}</h3>
      <p>{props.adParagraph1}</p>
      <p>{props.adParagraph2}</p>
    </div>
  );
```

The purpose of the template-like functional component is to pass data:

- The React functional component element, `<Adcomponent ... />` allows attributes. The attribute values are passed to the template-like component through the attribute name to change components data.

- Select each React functional component element with an **id selector**. For example, `document.querySelector("#ad1")`.

In **HTML** and **JSX**, the code source of the bottom three components is shown below:

**HTML**
```html
<section>
  <div class='component-1 component'>
    <div id='ad1'></div>
  </div>

  <div class='component-2 component'>
    <div id='ad2'></div>
  </div>
  
  <div class='component-3 component'>
    <div id='ad3'></div>
  </div>
</section>
```

**JSX**
```jsx
ReactDOM.render(
  <Adcomponent
    adHeading="Declarative"
    adParagraph1="React makes it painless to create interactive UIs..."
    adParagraph2="Declarative views make your code more predictable..."
  />,
  document.querySelector("#ad1")
);

ReactDOM.render(
  <Adcomponent
    adHeading="Component-Based"
    adParagraph1="Build encapsulated components that manage their..."
    adParagraph2="Since component logic is written in JavaScript..."
  />,
  document.querySelector("#ad2")
);

ReactDOM.render(
  <Adcomponent
    adHeading="Learn Once, Write Anywhere"
    adParagraph1="We don't make assumptions about the rest..."
    adParagraph2="React can also render on the server..."
  />,
  document.querySelector("#ad3")
);
```

The overall **JSX** code is shown below:

```jsx
const Adcomponent = props => {
  return (
    <div className="component-1 component">
      <h3>{props.adHeading}</h3>
      <p>{props.adParagraph1}</p>
      <p>{props.adParagraph2}</p>
    </div>
  );
};

ReactDOM.render(
  <Adcomponent
    adHeading="Declarative"
    adParagraph1="React makes it painless to create interactive UIs..."
    adParagraph2="Declarative views make your code more predictable..."
  />,
  document.querySelector("#ad1")
);

ReactDOM.render(
  <Adcomponent
    adHeading="Component-Based"
    adParagraph1="Build encapsulated components that manage their..."
    adParagraph2="Since component logic is written in JavaScript..."
  />,
  document.querySelector("#ad2")
);

ReactDOM.render(
  <Adcomponent
    adHeading="Learn Once, Write Anywhere"
    adParagraph1="We don't make assumptions about the rest..."
    adParagraph2="React can also render on the server..."
  />,
  document.querySelector("#ad3")
);
```
- We write even lesser code with **HTML** and **JSX** files when components are mounted in a root element, `<div id='root'></div>`.

**HTML**
```html
<div id='root'></div>
```

**JSX**
```jsx
const Adcomponent = props => {
  return (
    <div className="component-1 component">
      <h3>{props.adHeading}</h3>
      <p>{props.adParagraph1}</p>
      <p>{props.adParagraph2}</p>
    </div>
  );
};

const app = (
  <section>
    <Adcomponent
      adHeading="Declarative" 
      adParagraph1="React makes it painless to create interactive..." 
      adParagraph2="Declarative views make your code more..."
    />
    <Adcomponent
      adHeading="Component-Based" 
      adParagraph1="Build encapsulated components that manage their..." 
      adParagraph2="Since component logic is written in JavaScript..."
    />
    <Adcomponent
      adHeading="Learn Once, Write Anywhere" 
      adParagraph1="We don't make assumptions about the rest..."
      adParagraph2="React can also render on the server..." />
  </section>
);

const rootNode = document.querySelector("#root");
ReactDOM.render(app, rootNode);
```

The [above code snippet](https://codepen.io/techstack/pen/wvzyYWb) shows we can render components once in an application.

---
### Terminology
#### JSX
> JSX stands for JavaScript XML. **JSX** allows us to write HTML-like in Babel (JavaScript)

It is a custom **HTML** made available by React, but behind the scene is compiled to JavaScript. **JSX** is just a **syntactical sugar** featured in React.

#### ReactDOM
> ReactDOM is a package that provides **DOM** (**Document Object Model**) specific methods that can be used at the top level of a web app to enable an efficient way of managing DOM elements of the web page.

**ReactDOM** provides the developers with API methods, properties, objects, etc. For example, the `.render()` method on the ReactDOM object.

#### Props
> Props are arguments passed into React components. Props are passed to components via **HTML** attributes.

It makes changes in a **state** possible when components or an app is rendered to the screen.

#### Babel
> **[Babel](https://babeljs.io/)** is a free and open-source JavaScript transcompiler that is mainly used to convert ECMAScript 2015+ code into a backward-compatible version of JavaScript that can be run by older JavaScript engines

It takes care of **CSS auto-prefix** and **browser compatibility** (**CSS** and JavaScript). That is, writes code that works across all browsers. 

It is a popular tool for using the newest features of the JavaScript programming language (ECMAScript 2015+).

After the installation of React, via any package manager like **Node Package Manager** (**NPM**), there are lots of packages and dependencies you will find in the *.json* files. For example, **[webpack](https://webpack.js.org/)** comes with other packages.

#### Webpack
> Webpack is a module bundler. Its main purpose is to bundle JavaScript files for usage in a browser, yet it is also capable of transforming, bundling, or packaging just about any resource (asset)


[Edit on Codepen](https://codepen.io/techstack/pen/MWjvJjg)

*Click the Babel file button then click View Compiled button to see how React compiles **JSX** (Custom **HTML**) to JavaScript behind the scene*

**Happy Coding!!!**

---
[![Buy me a Coffee](https://res.cloudinary.com/bizstak/image/upload/v1610317510/ko-fi-trans_fr3su4.png)](https://www.buymeacoffee.com/bellotech)

---
#### Techstack | Flutterwave 
Techstack article, sponsored by Flutterwave. Flutterwave is the easiest way to make and accept payments both online and offline from customers anywhere in the world. It is absolutely free!  Also, you get a Flutterwave dollar barter card when you [signup](https://dashboard.flutterwave.com/signup?referrals=RV686851). Open an online store and take your business anywhere in the world.

Check out the [short demo](https://youtu.be/ClXVUM3Rf7A)

[Sign up](https://dashboard.flutterwave.com/signup?referrals=RV686851) today to get started

[Support](https://dashboard.flutterwave.com/donate/3lo9klliqwbu) what I do and push me to keep making free content.
