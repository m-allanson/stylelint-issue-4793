# stylelint-issue-4793

## About

A reproduction for [stylelint issue #4793](https://github.com/stylelint/stylelint/issues/4793)

Note that this error is triggered by using a [tagged template expression](https://babeljs.io/docs/en/babel-types#taggedtemplateexpression) or [call expression](https://babeljs.io/docs/en/babel-types#callexpression) named `html`. You could replace the contents of `index.js` with `html();` (a call expression) to trigger the same error.

## Getting started

- clone this repo
- run `npm install`
- run `npm run s`
- observe error output:

```
stylelint-issue-4793 on  master [?] took 8s
❯ npm run s

> stylelint-issue-4793@1.0.0 s /d/temp/stylelint-issue-4793
> stylelint "*.js"

TypeError: result.apply is not a function
    at /d/temp/stylelint-issue-4793/node_modules/@stylelint/postcss-css-in-js/extract.js:266:20
    at Array.some (<anonymous>)
    at isStylePath (/d/temp/stylelint-issue-4793/node_modules/@stylelint/postcss-css-in-js/extract.js:257:33)
    at TaggedTemplateExpression (/d/temp/stylelint-issue-4793/node_modules/@stylelint/postcss-css-in-js/extract.js:351:8)
    at NodePath._call (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/path/context.js:55:20)
    at NodePath.call (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/path/context.js:42:17)
    at NodePath.visit (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/path/context.js:90:31)
    at TraversalContext.visitQueue (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/context.js:112:16)
    at TraversalContext.visitSingle (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/context.js:84:19)
    at TraversalContext.visit (/d/temp/stylelint-issue-4793/node_modules/@babel/traverse/lib/context.js:140:19)
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! stylelint-issue-4793@1.0.0 s: `stylelint "*.js"`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the stylelint-issue-4793@1.0.0 s script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /.npm/_logs/2020-06-02T15_33_08_304Z-debug.log
```
