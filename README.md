# Welcome To The Repro

## Expected

Both the Google and Local fonts should have a link rel preload in the first HTML sent back from the server

## Actual

Neither font has a preload entry in the first HTML sent back from the server and they aren't downloaded until the CSS references them.

# To See The Repro

```
npm run build
npm run start
```

Navigate to localhost:3000 in dev tools in Chrome and observe the absence of a preload for the fonts in the initial HTML response.

# Steps applied in this repository to create this repro

Create the app 'repro' with all defaults:

```
npx create-next-app@latest
```

Put a font file in the root [repro/SpaceGroteskTrimmed.woff2](./repro/SpaceGroteskTrimmed.woff2)

Reference it in [repro/app/layout.ts](./repro/app/layout.tsx)

# Workaround

I've had to manually add &lt;link&gt; statements to &lt;head&gt; in my app's layout.tsx to preload the fonts.
