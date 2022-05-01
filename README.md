This repo contains a template for a minimal [Next.js](https://nextjs.org/) application with the development environment enhanced by [gts](https://www.npmjs.com/package/gts).

## Why Next.js?

Here's how Vercel describes Next.js:

**The React Framework
for Production.**
Next.js gives you the best developer experience with all the features you need for production: hybrid static & server rendering, TypeScript support, smart bundling, route pre-fetching, and more. No config needed.

## Why GTS?

Here's the pitch from the NPM page:

[gts](https://www.npmjs.com/package/gts) is Google's TypeScript style guide, and the configuration for our formatter, linter, and automatic code fixer. No lint rules to edit, no configuration to update, no more bike shedding over syntax.

To borrow from [standardjs](https://www.npmjs.com/package/standard):

* No configuration. The easiest way to enforce consistent style in your project. Just drop it in.
* Automatically format code. Just run gts fix and say goodbye to messy or inconsistent code.
* Catch style issues & programmer errors early. Save precious code review time by eliminating back-and-forth between reviewer & contributor.
* Opinionated, but not to a fault. We recommend you use the default configuration, but if you need to customize compiler or linter config, you can.

Under the covers, we use eslint to enforce the style guide and provide automated fixes, and prettier to re-format code.

---
You can copy over the template verbatim, but I recommend creating it using the steps, listed below. The steps are simple, consisting of two `npx` commands, a folder deletion, and two file edits.

Some parts of the repo were adapted from ideas in this [guide to configuring Next.js with GTS](https://iiiyu.com/2021/06/08/how-to-set-up-a-nextjs-project-with-typescript/).

# Create Next.js App

Use `npx` to run create-next-app. In this example, the last argument is the path where the Next.js application will be created. Note that `create-next-app` will also initialize a git repo.

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

# Install and Configure GTS

Use `npx` to run `gts init`:
~~~bash
% npx gts init
~~~

Answer `no` to each of the prompts about overwriting existing dependencies and files.
Here's the output:
~~~bash
version: 16
Already have devDependency for typescript:
-4.6.4
+^4.0.3
? Overwrite No
Already have devDependency for @types/node:
-17.0.31
+^14.11.2
? Overwrite No
package.json already has a script for lint:
-next lint
+gts lint
? Replace No
Writing package.json...
{
  scripts: {
    dev: 'next dev',
    build: 'next build',
    start: 'next start',
    lint: 'next lint',
    clean: 'gts clean',
    compile: 'tsc',
    fix: 'gts fix',
    prepare: 'npm.cmd run compile',
    pretest: 'npm.cmd run compile',
    posttest: 'npm.cmd run lint'
  },
  devDependencies: {
    '@types/node': '17.0.31',
    '@types/react': '18.0.8',
    '@types/react-dom': '18.0.3',
    eslint: '8.14.0',
    'eslint-config-next': '12.1.5',
    typescript: '4.6.4',
    gts: '^3.1.0'
  }
}
./tsconfig.json already exists
? Overwrite No
./.eslintrc.json already exists
? Overwrite No
Writing ./.eslintignore...
build/

Writing ./.prettierrc.js...
module.exports = {
  ...require('gts/.prettierrc.json')
}

Default template installed.

added 214 packages, and audited 445 packages in 12s

103 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
~~~

Add the following line to the `tsconfig.json`:
~~~json
{
  ...
  "extends": "./node_modules/gts/tsconfig-google.json",
  ...
}
~~~

Remove `src/index.ts` and the empty `src` folder:
~~~bash
% rm src/index.ts
% rmdir /s src
~~~

# Configure VS Code

Create `.vscode/settings.json`:

~~~json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.detectIndentation": false,
  "editor.insertSpaces": true,
  "editor.renderWhitespace": "all",
  "editor.tabSize": 2,
  "[javascript]": {
    "editor.formatOnSave": true
  },
  "[javascriptrect]": {
    "editor.formatOnSave": true
  },
  "[json]": {
    "editor.formatOnSave": true
  },
  "[typescript]": {
    "editor.formatOnSave": true
  },
  "[typescriptreact]": {
    "editor.formatOnSave": true
  }
}
~~~

# Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

