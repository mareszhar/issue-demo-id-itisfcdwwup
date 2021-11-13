# How to Recreate The Issue

1. Clone this repository and run `npm install`
2. Run `npm run dev`
3. If you go to the local server url, you will see a blank page. If you
   inspect the page with the console, you should see the following error:
   `The requested module '/src/types.ts' does not provide an export named 'Character'`

It seems that something in Vite's handling of Pug is causing the problem.
If you have the extension Volar enabled and can see a 'Pug' checkbox on top
of the `<template>` tag in App.vue, you can try toggling it to switch back
to html format. Then, restart your dev server and the problem should go away.

# Any ideas on how to fix this?

Although the issue is triggered by using Pug, I suspect the problem is with
Vite's handling of Pug. After all, it would be weird for Pug to be responsible
for issues with imports in the `<script>` tag area!

Also, I should note that, if you run `npm run serve` instead and check out
the local server url then, you'll see that there isn't any issue even if you used
Pug in your `<template>`. There also isn't any problem in the final output of
`npm run build` either. Vite is only having issues handling imports of
non-javascript elements (like a TypeScript interface) when using the dev server.

I've been using the Vue CLI for a while before trying out Vite, and it didn't have
this issue when coding with hot module replacement. Vite is so much faster at HMR,
so I hope I don't have to give up on it.

Any help is very much appreciated!
