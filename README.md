This repo contains a template for a minimal [Next.js](https://nextjs.org/) application. The remainder of this file documents the steps used to create the template.

# Create Next.js App

Use `npx` or `yarn` to create the Next.js application. In this example, the last argument is the path where the Next.js application will be created. Note that `create-next-app` will also initialize a git repo.

~~~bash
% npx create-next-app@latest --typescript next-gts-bootstrap
~~~

Here's the console output:
~~~bash
Creating a new Next.js app in D:\git\starter\next-gts-bootstrap.

Using npm.

Installing dependencies:
- react
- react-dom
- next


added 14 packages, and audited 15 packages in 2s

2 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

Installing devDependencies:
- eslint
- eslint-config-next
- typescript
- @types/react
- @types/node
- @types/react-dom


added 216 packages, and audited 231 packages in 5s

66 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

Initialized a git repository.

Success! Created next-gts-bootstrap at D:\git\starter\next-gts-bootstrap
Inside that directory, you can run several commands:

  npm run dev
    Starts the development server.

  npm run build
    Builds the app for production.

  npm start
    Runs the built app in production mode.

We suggest that you begin by typing:

  cd next-gts-bootstrap
  npm run dev
~~~

At this point the Next.js application is fully configured and you can try it out in the dev server:

~~~bash
% npm run dev

> next-gts-bootstrap@0.1.0 dev
> next dev

ready - started server on 0.0.0.0:3000, url: http://localhost:3000
wait  - compiling...
event - compiled client and server successfully in 1892 ms (124 modules)
~~~

# Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

