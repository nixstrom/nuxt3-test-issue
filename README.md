# Nuxt 3 - Testing Issue

This is a repo to demonstrate a potential bug with Nuxt 3, in which test files are being bundled for production builds, causing the entire app to fail due to missing Jest globals.

## Reproduction

### 1. Install the dependencies

```bash
yarn
```

### 2. Create a dev build (optional)

This is just to verify the code is in fact working. This will be available on http://localhost:3000

```bash
yarn dev
```

### 3. Create a production build

```bash
yarn build
```

### 4. Serve the build

```bash
node .output/server/index.mjs
```

## Expected outcome

The app will be served, just like when running the dev build.

## Actual outcome

The app will fail with the error `describe is not defined`.

## Further observations

1. Deleting the test file or moving it to a non-Nuxt directory (e.g. `~/__tests/`) will fix the issue.
2. Instructing the test files to be ignored, either in `.nuxtignore` or in `nuxt.config.ts` does nothing. According to JS Doc, thwy should in fact be ignored by default.
3. Renaming the test file to something else (e.g. `-Button.test.vue` or `Button.spec.ts` does not solve the issue).
