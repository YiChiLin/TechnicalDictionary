# Init simple web with webpack and babel

### Webpack install

```bash
npm init -y (Created package.json without answer questions)
npm i webpack webpack-cli --save-dev
```

- webpack command (setup in package.json script seciton)

  - "start": "webpack --mode development" (run for local dev environment)
  - "build": "webpack --mode production"

- webpack dev-server

```bash
    npm i webpack-dev-server --save-dev
```

- webpack command (setup in package.json script seciton)

  - "start": "webpack-dev-server --mode development" (run for local dev environment)

### Babel install

- It is a transpiler from new js version(ES6) to the most compatible version(ES5)

```bash
npm i babel-core@6.26.3 babel-loader@7.1.4 babel-preset-env@1.7.0 --save-dev
```
