# Playwright bug test

This repository is a test project for reproducing bug 
[#32868](https://github.com/microsoft/playwright/issues/32868)
in Playwright project.

The project is based on Remix and a minimal Playwright setup built for reproducing the bug. 

## Steps to reproduce

1. Clone this repo.
2. Install dependencies with `yarn`
3. Run tests in CLI mode by executing: `yarn test`
4. Run the same tests in UI mode by executing: `yarn test:ui`

### Expected behaviour

When Playwright is run with `--ignore-snapshots` flag, `expect(locator).toHaveScreenshot()` is always ignored, as described in the docs.

### Actual behavior

Test fails on snapshot comparison when `--ignore-snapshots` flag is used together with `--ui` flag.

---

### The rest of this document refers to the project development in Remix.

## Development

Run the dev server:

```shellscript
npm run dev
```

## Deployment

First, build your app for production:

```sh
npm run build
```

Then run the app in production mode:

```sh
npm start
```

Now you'll need to pick a host to deploy it to.

### DIY

If you're familiar with deploying Node applications, the built-in Remix app server is production-ready.

Make sure to deploy the output of `npm run build`

- `build/server`
- `build/client`

## Styling

This template comes with [Tailwind CSS](https://tailwindcss.com/) already configured for a simple default starting experience. You can use whatever css framework you prefer. See the [Vite docs on css](https://vitejs.dev/guide/features.html#css) for more information.
