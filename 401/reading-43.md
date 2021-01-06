# Next.js App
https://nextjs.org/learn/basics/create-nextjs-app

## Next.js: The React Framework

many built-in features:

- An intuitive page-based routing system (with support for dynamic routes)

- Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis

- Automatic code splitting for faster page loads

- Client-side routing with optimized prefetching

- Built-in CSS and Sass support, and support for any CSS-in-JS library

- Development environment with Fast Refresh support

- API routes to build API endpoints with Serverless Functions

- Fully extendable

## Setup

need Node.js version 10.13 or later.

to create an next app: 
```
npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/learn-starter"
```
cd into the new app

run app with: ``` npm run dev ```

## Welcome

you should be able to see your newly created app in the localhost Port that it is running from

hit control c to restart the server

edit the starter page by changing the index.js page

## Navigating

``` npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/navigate-between-pages-starter" ```

add new pages with new slash routes in the pages directory

```
export default function FirstPost() {
  return <h1>First Post</h1>
}
```

## Link Components
should be wrapped in an <a> tag

should have an end point reference

``` import Link from 'next/link'```

find the h1 tag: ```

<h1 className="title">
  Learn <a href="https://nextjs.org">Next.js!</a>
</h1>
```
 and change it:
 
 ``` <h1 className="title">
  Read{' '}
  <Link href="/posts/first-post">
    <a>this page!</a>
  </Link>
</h1>```

set up new content:
```v
Navigate Between Pages
Link Component
When linking between pages on websites, you use the <a> HTML tag.

In Next.js, you use the Link Component from next/link to wrap the <a> tag. <Link> allows you to do client-side navigation to a different page in the application.

Using <Link>
First, open pages/index.js, and import the Link component from next/link by adding this line at the top:

import Link from 'next/link'
Then find the h1 tag that looks like this:

<h1 className="title">
  Learn <a href="https://nextjs.org">Next.js!</a>
</h1>
And change it to:

<h1 className="title">
  Read{' '}
  <Link href="/posts/first-post">
    <a>this page!</a>
  </Link>
</h1>
{' '} adds an empty space, which is used to divide text over multiple lines.

Next, open pages/posts/first-post.js and replace its content with the following:

import Link from 'next/link'

export default function FirstPost() {
  return (
    <>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}```
