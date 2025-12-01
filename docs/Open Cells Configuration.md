# Open Cells – Configuration

### Initialization

The `startApp` function from Open Cells core is essential for initializing your application. This function requires a configuration object that must include at least:

- `routes`: The [routing](/docs/routing/routes/index.html) definitions for your application.
- `mainNode`: The ID of the HTML element in the main document where the pages will be rendered.

Optional properties:

- `viewLimit`: Maximum number of pages present in the DOM at the same time.
- `persistentPages`: Names of pages that should not be removed from the DOM.
- `interceptor`: Function to intercept and possibly modify routing behavior.
- `appConfig`: Object to store specific application configurations.
- `commonPages`: Names of pages that should be pre-registered.

### Application Configuration

Applications can use the `appConfig` property within the configuration object to tailor settings specific to their requirements. Open Cells core provides `getConfig()` to retrieve the current configuration object at any time.

#### Example

_Define configuration:_

```ts
startApp({
  routes,
  mainNode: 'app-content',
  // application’s config properties
  appConfig: {
    allowGuestMode: true,
    country: { lang: 'es-ES', timeZone: 'GMT+2' },
  },
});
```

_Retrieve configuration:_

```ts
import { getConfig } from '@open-cells/core';
const { appConfig } = getConfig(); // Retrieve the current configuration object
const lang = appConfig.country.lang; // Access language setting
```

### Organizing Configuration Files

For large apps, organize configuration into separate modules and import them where you call `startApp`.

```ts
import { startApp } from '@open-cells/core';
import { routes } from '../router/routes.js';
import { appConfig } from '../config/app-config.js';

startApp({
  mainNode: 'app-content',
  routes,
  appConfig,
});
```

- Code licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
- Documentation licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)

© Banco Bilbao Vizcaya Argentaria, S.A. 2024
