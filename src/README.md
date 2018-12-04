# What is Server Side Rendering or SSR

- The process of taking a client side javascript framework website and rendering it as static html and css on the server
- Helps you render your website faster
- This is the traditional, old school way of rendering an application.
- Modern day javascript frameworks like Vue and React leverage a concept known as a client side rendering (CSR)
- The concept of having javascript on both the server and client is known as Isomorphic or Universal javascript, meaning it can run both on the server and the client.

## The critical path

- the process of delivering the most important content to the browser so it can render a page
- how fast the browser renders an app is determined by how you build it
- the browser receives an html document and parses it, learning where to find assets such as images, css, and javascript
- even though the browser has your website, it can't render it until the browser has the html and css
- after the html is parsed, the browser parses the javascript
- the parsing times are determined by the client's hardware and network speed.
- Client side frameworks have large javascript files that tie up the rendering code
- they can be fast if you're willing to put in the work
- we can generate the html on the server and send it to the browser so the user will see the app immediately, while the javascript app boots up in the background
- while this may not make your page / app load faster than a non-ssr version, it does give the users something to look at while its booting up

### cost of this benefit

- there is time and effort thats needed on the server to generate these documents
- however, you can configure a server to cache these documents after the initial generation
- the browser will still need to parse and execute the javascript in order for the application to be interactive

- performance for ssr can vary per user - internet speed, active users at a given time, server location, page optimization
- wheras client side rendering (csr) will have a longer initial load time, the factors listed above won't have any bearing on the user interactivity.

### SEO benefits

- while having an application that is rendered on the client using a fancy framework makes both the lives of developers more enjoyable, as well as a snappy experience for users (once the javascript document is parsed), csr does come at a potentially costly loss in search engine optimization (SEO)

- Google crawls sites in a 2 wave process for JS rendering and indexing.
- the first wave requests the source code, crawls & indexes any present HTML & CSS and adds the links to the crawl queue and then downloads page responses

- on a CSR site, there is basically nothing for Google to index in the source code at this point.
- A vue app looks a little something like this: `<div id="app"></div>`
- The second wave can occurr a few hours to even weeks later, when additional resources are available to fully render and index the JS generated content

- Essentially, with SSR, there is generally no issue with Google's rendering delay because the content is all in the source code. In CSR, the content is displayed at render, meaning that content and updates may not appear in search results for days or even weeks.

# src

> Nuxt.js project

## Build Setup

```bash
# install dependencies
$ npm install # Or yarn install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).
