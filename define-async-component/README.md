# defineAsyncComponent Demo

A single HTML file showing how Vue 3's `defineAsyncComponent` works.

## Run it

Open `async-component-demo.html` in a browser. Nothing to install.

## What it does

Simulates loading a component from a server (1.5s delay) so you can see:

- **Load successfully** → shows a loading message, then the component
- **Simulate failure** → shows a loading message, then an error message

## How it maps to real code

```js
defineAsyncComponent({
  loader: () => import('./MyComponent.vue'), // fetch the component
  loadingComponent: LoadingComp,             // shown while waiting
  errorComponent: ErrorComp,                 // shown if it fails
  timeout: 5000                              // give up after 5s
})
```

The demo fakes `loader` with a delayed Promise instead of a real import, since real `.vue` imports need a bundler (Vite/webpack) — not just a browser.

## Things to watch out for

- Only helps if the component *isn't* needed right away (e.g. a modal, not the header).
- Skip `loadingComponent`/`errorComponent` and failures/delays show nothing.
- `<Suspense>`, if used, overrides these loading/error options.
- Retrying a failed load isn't automatic — the error component gets a `retry` function you have to hook up yourself.
