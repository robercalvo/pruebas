# Open Cells - Frontend Framework
### This website uses cookies form Google

We only use them to analyse traffic and understand how to improve our website. We do not store personal data.

Detailed information

**Statistical cookies**  
Statistical cookies help website owners understand how visitors interact with websites by gathering and providing information in an anonymous form.

**GOOGLE**  
[More about Google’s cookies](https://policies.google.com/technologies/cookies)

- _ga — It records a unique ID that is used to generate statistical data about how the visitor uses the website. Expiration: 2 years · Type: HTTP
- _ga_# — Collects data on the number of times a user has visited the website as well as the dates of the first and most recent visit. Used by Google Analytics. Expiration: 2 years · Type: HTTP
- _gat — Used by Google Analytics to monitor request rates. Expiration: 1 day · Type: HTTP
- _gid — It records a unique ID that is used to generate statistical data about how the visitor uses the website. Expiration: 1 day · Type: HTTP
- collect — Used to send data to Google Analytics about the visitor's device and behaviour. Tracks visitor across devices and marketing channels. Expiration: Session · Type: Pixel
- td — It records statistical data on visitor behaviour on the website. This is used for internal analysis by the website operator. Expiration: Session · Type: Pixel

---

**Navigation**

- EN | ES
- [Documentation](./docs/index.html) · [Github](https://github.com/BBVA/open-cells) · Search

**Sections**

- Introduction → [What is Open Cells?](/docs/index.html), [Getting Started](/docs/getting-started/index.html)
- Application → [Bootstrapping](/docs/application/bootstrapping/index.html), [Configuration](/docs/application/configuration/index.html)
- State → [Channels](/docs/state/channels/index.html), [Controllers](/docs/state/controllers/index.html), [Bounded Properties](/docs/state/bounded-props/index.html), [Page Mixin](/docs/state/page-mixin/index.html)
- Routing → [Routes](/docs/routing/routes/index.html), [Rendering](/docs/routing/rendering/index.html), [Interceptor](/docs/routing/interceptor/index.html)
- Transitions → [Page Transitions](/docs/transitions/page-transitions/index.html)
- Interoperability → [Lit Integration](/docs/interoperability/lit-integration/index.html), [Web Components Libraries](/docs/interoperability/web-components/index.html)
- Localization → [i18n & localization](/docs/localize/i18n-localization/index.html)

---

## What is Open Cells?

Open Cells is a JavaScript framework for building Single Page Applications based on web components. It builds on top of standard HTML, CSS and JavaScript and provides a declarative, component-based programming model with [Web Components](https://www.webcomponents.org/introduction) at the heart of it. This approach embraces reusability and interoperability, which helps efficiently develop user interfaces of any complexity.

As Open Cells is an architecture built over the idea that instead of building monolithic applications it is better to build a set of reusable components (business modules) that are assembled and communicate with each other to create applications.

### Minimal example

```ts
import { startApp } from '@open-cells/core';

// Define routes and other necessary configurations
const routes = [
  {
    path: '/',
    name: 'home',
    component: 'home-page',
    action: async () => {
      await import('../pages/home/home-page.js');
    },
  },
];

// Execute startApp with necessary options
startApp({
  routes,
  mainNode: 'app-content',
});
```

```html
<div id="app-content"></div>
```

### Open Cells ecosystem

Open Cells revolves around two main concepts: a core library, and Web Components as componentization model.

#### Core

Open Cells core is the library that provides applications with:

- State management through the use of pub/sub messaging pattern
- Routing mechanism
- App Configuration
- Bootstrapping

If your application logic involves extensive data communication among components, you can take full advantage of this architecture.

#### Web Components

Open Cells uses Web Components as its componentization model. Although app pages are built using Lit, any kind of Web Component can be used inside them, from vanilla ones to others built using Lit or other libraries.

You can explore an extensive collection of [Web Components](https://www.webcomponents.org/) available or create your own ones to work with. Check our specific [Web Components Libraries](/docs/interoperability/web-components/index.html) section to find out about some of the libraries that can be used.

### License

Open Cells is available under the terms of the Apache-2.0 license.

- Code licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
- Documentation licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)

© Banco Bilbao Vizcaya Argentaria, S.A. 2024
