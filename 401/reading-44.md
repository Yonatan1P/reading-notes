# Next.js Continued

## Pre-Rendering and DAta Fetching

setup from 
``` npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/data-fetching-starter"```

pre-rendering allows for the page to display something before being fully rendered

2 types, static and server-side

one stays up all the time, and the other is prepared before the request on the server side.

static file can be generated with or without data, but need to wait for the data to come in if they are using data

you can get the static properties from these pages

to parse meta data, install "grey-matter"

pre-render, then make the async calls to the APIs, then fully render all the data

## Dynamic Routes

starter code: ```npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/dynamic-routes-starter"```

if you want dynamic pages, you need to fetch the page data and the static input data

you want to get the static pages and the static props

make a function that can ge tthe static path from the front end side.
