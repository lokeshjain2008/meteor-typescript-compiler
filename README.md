# Meteor Typescript Compiler

Adds TypeScript compiler to Meteor projects.

## Change Log

 * 3.1.0: updated to be based on [typescript](https://github.com/barbatus/typescript) package.

## Installation

Just run `meteor add meteortypescript:compiler` to add TypeScript compiler to your project.

That's it! From now on, all TypeScript files will be dynamically compiled into Javascript.

Compatible with Meteor 1.2.1 and Meteor 1.3.

Notice that ES6 modules are compiled into CommonJS modules by default (see below for more).

## TypeScript Options

TypeScript is transpiled into ECMAScript 5 and CommonJS modules by default.

All together default TypeScript compiler options of this compiler are:

````json
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es5",
    "moduleResolution": "node",
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,
    "sourceMap": true
  }
}
````

If you want to customize options, add `tsconfig.json` file to the root of your app.
For more about available compiler options, please refer to the official [docs](http://www.typescriptlang.org/docs/handbook/compiler-options.html).

## Typings

Recommended way to install typigns is to use typings tool.

For example, to install Meteor declaration files, you'll need to run commands as follows:

````
npm install typings -g

typings install meteor --ambient
````

Current compiler doesn't make difference between declaration and regular TypeScript files and processes them all.

Also, it sticks to the Meteor isomorphic environment which means it compiles files architercture-wise.

Or in other words, if you put declaration files, for example, in the server folder, they will be used for the server side code only.
