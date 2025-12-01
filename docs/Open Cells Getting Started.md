# Open Cells – Getting Started

This page describes how to start developing an app with Open Cells.

## App creation

```bash
npm init @open-cells/app
```

Choose between an empty application (minimal sample) or a full sample application (cooking recipes). Then enter a name; a folder will be created with the application inside.

**Generated structure**

```
Root Directory/
├── package.json
├── tsconfig.json
├── index.html
├── images/
│   └── favicon.svg
└── src/
    ├── components/
    │   ├── app-index.ts
    │   └── app-index.css.js
    ├── pages/
    │   ├── home/
    │   │   └── home-page.ts
    │   └── second/
    │       └── second-page.ts
    ├── css/
    │   ├── home.css
    │   ├── main.css
    │   └── second.css
    └── router/
        └── routes.ts
```

Install dependencies and run:

```bash
npm install
npm run dev
```

## App development

### App initialization

`index.html` contains the node where pages render and the tag that invokes Open Cells logic:

```html
<app-index id="app-content"></app-index>
```

`src/components/app-index.ts` imports the core library and initializes the app:

```ts
import { startApp } from '@open-cells/core';
import { routes } from '../router/routes.js';

startApp({
  routes,
  mainNode: 'app-content',
});
```

From there, focus on:

- **Pages and routes:** Define navigation.
- **Pages and components:** Build UI with Web Components.

### Pages and routes

`router/routes.ts` lists available pages and routes and is provided to `startApp`.

Each item maps a path to its page. There must always be an initial page at the root path `/`.

```ts
export const routes: object[] = [
  {
    path: '/',
    name: 'home',
    component: 'home-page',
    action: async () => {
      await import('../pages/home/home-page.js');
    },
  },
  {
    path: '/second',
    name: 'second',
    component: 'second-page',
    action: async () => {
      await import('../pages/second/second-page.js');
    },
  },
];
```

Handle invalid routes if needed; see **Routing** docs. Transitions animate navigation; see **Page Transitions**.

### Adding new pages

Create `src/pages/about/about-page.ts` and add it to `routes.ts`:

```ts
{ path: '/about', name: 'about', component: 'about-page', action: async () => { await import('../pages/about/about-page.js'); } },
```

Pages are Lit components:

```ts
import { LitElement, html, css } from 'lit';
import { customElement } from 'lit/decorators.js';

@customElement('about-page')
export class AboutPage extends LitElement {
  static styles = css`
    /* CSS styles for your page */
  `;
  render() {
    return html`<!-- HTML content for your page -->`;
  }
}
```

Add components (e.g., Material Web):

```bash
npm i --save @material/web
```

```ts
import '@material/web/button/outlined-button.js';
```

```ts
render() {
  return html`
    <h2>About page with a button</h2>
    <md-outlined-button>Material button</md-outlined-button>
  `;
}
```

### Open Cells controllers

Use page/element controllers for pub/sub, navigation, and lifecycle hooks (`onPageEnter`, `onPageLeave`).

```ts
import { PageController } from '@open-cells/page-controller';
import { html, LitElement, css } from 'lit';
import { customElement, state } from 'lit/decorators.js';
import '@material/web/button/outlined-button.js';

@customElement('about-page')
export class AboutPage extends LitElement {
  pageController = new PageController(this);
  @state() protected _randomData = null;

  onPageEnter() {
    this.pageController.subscribe('ch-custom-data', data => {
      this._randomData = data;
    });
  }
  onPageLeave() {
    this.pageController.unsubscribe('ch-custom-data');
  }

  static styles = css``;
  render() {
    return html`
      <h2>About page with a button</h2>
      <md-outlined-button @click="${() => this.pageController.navigate('home')}">Go to home page</md-outlined-button>
      <p>My _randomData: ${this._randomData}</p>
    `;
  }
}
```

Publish data and navigate from Home:

```ts
onPageEnter() {
  this.pageController.publish('ch-custom-data', "Hello! I'm a channel value!");
}
render() {
  return html`
    <button @click="${() => this.pageController.navigate('second')}">Go to second page</button>
    <button @click="${() => this.pageController.navigate('about')}">Go to about page</button>
  `;
}
```

### App configuration

`startApp` expects `routes` and `mainNode`. You can also pass `appConfig`.

```ts
import { startApp } from '@open-cells/core';
import { routes } from '../router/routes.js';

startApp({
  routes,
  mainNode: 'app-content',
  appConfig: {},
});
```

### Build & serve

Open Cells uses [Vite](https://vitejs.dev/).

```bash
npm run build   # build
npm run dev     # serve locally
```

- Code licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
- Documentation licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)

© Banco Bilbao Vizcaya Argentaria, S.A. 2024
