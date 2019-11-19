<p align="center"><img src="./assets/icon.png"></p>
<h2 align="center">Playground</h2>
<p align="center">
<strong>A simple playground for HTML, CSS and JavaScript supporting module imports.</strong>
<br>
<a href="https://www.npmjs.com/package/@agney/playground">
  <img src="https://badge.fury.io/js/%40agney%2Fplayground.svg" />
</a>
<img src="https://img.shields.io/badge/module%20formats-umd%2C%20cjs%2C%20esm-green.svg" />
<br />
<a href="https://github.com/BoyWithSilverWings/playground/actions">
  <img src="https://github.com/BoyWithSilverWings/playground/workflows/Node%20CI/badge.svg" />
</a>
<a href="https://prettier.io">
  <img alt="code style: prettier" src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square" />
</a>
<a href="http://makeapullrequest.com">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" />
</a>
<br>

**Playground** is a HTML, CSS and JS demonstration component that runs entirely in the browser and does not require loading any third party sites.

## Usage

Install from `npm` with `npm install @agney/playground` or `yarn add @agney/playground`

```jsx
import Playground from "@agney/playground";

const App = () => {
  const snippet = {
    markup: `<div id=app />`,
    css: ``,
    javascript: `import { h, Component, render } from 'preact';
import htm from 'htm';

const html = htm.bind(h);

const app = html\`<div>Hello World from Playground!</div>\`

render(app, document.getElementById('app'));
    `,
  };
  return (
    <Playground
      id="example"
      initialSnippet={snippet}
      defaultEditorTab="javascript"
    />
  );
};
```

## Demo

> Soon

## Features

1. Autoreloading preview for change
2. Can load preview for predefined code.
3. Allows for ES module imports. This means you can add imports for any library that supports ES Module resolution and playground will automatically load it into your code.

## Applications

1. Add to static blogs to present your HTML, CSS or JavaScript code.
2. Allow users to change the code and see the output in real time. This could be big in educational articles and so.

## API

|      Props       |                                    description                                    | default  | required |
| :--------------: | :-------------------------------------------------------------------------------: | :------: | :------: |
|        id        |                        a unique identifier for the iFrame                         |          |   true   |
|  initialSnippet  |                           Initial code to be displayed                            |          |   true   |
| defaultEditorTab | Initial editor tab to be displyed. Possible values: "markup", "css", "javascript" | "markup" |  false   |
| defaultResultTab | Initial tab on result panel to be displayed. Possible values: "console", "result" | "result" |  false   |

### Format for initial snippet

```js
{
  markup: `<h1>Title</h1>`,
  css: `h1 { color: red }`,
  javascript: `console.log("this")`
}
```

### How does module imports work?

If an NPM package exposes an endpoint for "module", then you can direcly import this package by it's name.

```js
import { format } from "date-fns";

format(new Date(2014, 1, 11), "yyyy-MM-dd");
```

Unfortuantely, not all packages currently support this feature. You can search through an entire list of packages through [pika.dev](https://pika.dev).

You can use community created packages to replicate the functionality. For eg. React would be:

```js
import React, { createElement } from "@pika/react";
import ReactDOM from "@pika/react-dom";

ReactDOM.render(
  createElement("div", {}, "Hello World"),
  document.getElementById("app")
);
```

## What about the bundle size?

This component uses [Babel Standalone](https://babeljs.io/docs/en/babel-standalone) and it adds a considerable amount to the total bundle size. You can find the total size and time on [Bundle Phobia](https://bundlephobia.com/result?p=@agney/playground@0.1.0)

## Contributing

This project makes use of [Yarn Workspaces](https://yarnpkg.com/lang/en/docs/workspaces/) for development.

1. Run `yarn` for installing dependencies.

2. Run `yarn start` to start development on package.

3. To start example, run `yarn start-example`.

Pull Requests are Welcome. Please create an issue to discuss before making a feature or large change. Thank You :)

## Credits

<div>Icons made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a></div>
