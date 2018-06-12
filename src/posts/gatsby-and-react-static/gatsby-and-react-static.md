---
path: "/gatsby-and-react-static/"
date: "2018-06-12"
title: "Gatsby and React-static"
tags: ["gatsby", "react-static", "react"]
---

I have been wanting to start a blog for a while now. But I haven't come much further than writing incomplete pieces of text and researching which blogging tool is the best. It is properly a necessary detour that allows your brain to structure and formulate your thoughts into communicable formats. Writing is fundamentally a different exercise than the its precursor – reading – and it takes effort and will accomplish it. 

A static React site generator seems for me to be the best blogging tool available. It leverages technologies I know, is easy customizable and simplistic. They have the best performance and scalability of any blogging tool and that is while being free. For users with a Git work flow usability is excellent, I can write my blog posts in my favorite editor (Sublime), view it locally and deploy from the command line. You can write with minimal amount of distraction.

The most prominent static React generators are Gatsby and React-static. Both use React and share enough similarities to be considered competitors. In practical use, they differ considerable which is a deliberate choice and this is reflected in the default file structure of both.

## React-static 
Run `npm install -g react-static && react-static create` and install the basic boilerplate:

```javascript
- public/
  - robots.txt
- src/
  - App.js
  - app.css
  - containers/
    - 404.js
    - About.js
    - Blog.js
    - Home.js
    - Post.js
  - index.js
  - logo.png
- package.json
- static.config.js
- .babelrc
- .eslintrc.js
```

With React-static you get the familiar file structure known from `create-react-app` with the `react-static` package added, along with `react`, `react-dom` and `react-router`. React-static provides a simple API for attaching data to the React app with the configuration located in the `static.config.js` file. Customization and development are done like a regular React app, no abstractions. There are no `react-static` specific plugins, you will need to integrate various Node or React packages when developing features such as: code highlighting, image handling or RSS feed. In this sense, React-static is more a boilerplate or React package leveraging the React technology stack, than an actual static site generator. This is different in Gatsby.

## Gatsby
Run `npm i -g gatsby-cli && gatsby new my-app`:

```javascript
- public/
- src/
  - components/
    - header.js
  - layouts/
    - index.css
    - index.js
  - pages/
    - 404.js
    - index.js
    - page-2.js
- gatsby-browser.js
- gatsby-node.js
- gatsby-config.js
- gatsby-ssr.js
- package.json
```

The Gatsby has its own structure and deviates from the `create-react-app` boilerplate. `react`, `react-dom` and `react-router` aren't in the package.json file – like with React-static – but bundled with Gatsby. Multiple files: `gatsby-browser.js`, `gatsby-config.js`, `gatsby-node.js` and `gatsby-ssr.js` gives access to the Gatsby API. This includes adding Gatsby specific plugins or adding custom page types with data, fore instance a blog post template. Gatsby ships with GraphQL for data handling. Beyond the React style used in the `src/` files, there isn't much evidence that Gatsby is build on React.

## Comparison

Gatsby is essentially a static blog generator build on top of React with its own ecosystem, like Wordpress. Building a Gatsby site means using its plugins, API and documentation, not React's per-se. For blogs, personal or corporate web sites this speeds up development by making image handling, code highlighting or setting up a RSS feed dead simple. The documentation from development to deployment is good and easily accessible from their [web site](https://www.gatsbyjs.org/).

If Gatsby is build on top of React, React-static is build with React. Developing in React-static means developing a React application with data attached to it. It is simple to add data from a data source, but unlike Gatsby it doesn't come bundled with useful plugins for image handling, attaching files, code highlighting or adding Google analytics. To add such functionality means either coding it yourself or finding an npm package that does this. To add Markdown files as a data source you need to add: [jdown](https://github.com/DanWebb/jdown), [chokidar](https://github.com/paulmillr/chokidar), [htmr](https://github.com/pveyes/htmr) as shown in this [example](https://github.com/nozzle/react-static/tree/master/examples/markdown). This comes almost build in with Gatsby.

Choose Gatsby for a simple static web site and React-static if you want to add static data to your React app.
