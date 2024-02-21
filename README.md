# Steps applied in this repository

Create the app 'repro' with all defaults:

```
npx create-next-app@latest
```

Put a font file in the root [repro/SpaceGroteskTrimmed.woff2](./repro/SpaceGroteskTrimmed.woff2)

Reference it in [repro/app/layout.ts](./repro/app/layout.tsx)

```
npm run build
npm run start
```

Navigate to localhost:3000 in dev tools in Chrome

## Expected

Both the Google and Local fonts should have a link rel preload in the first HTML sent back from the server

## Actual

Neither font has a preload entry in the first HTML sent back from the server and they aren't downloaded until the CSS references them.

## Workaround

I've had to manually add &lt;link&gt; statements to preload the fonts.
