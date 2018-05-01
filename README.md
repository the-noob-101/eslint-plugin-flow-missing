# eslint-plugin-flow-missing

Mere ESLint plugin with one rule to check if one didn't forget to add the

```
// @ flow
```

header on each .js file. This rule was needeed not only because forgetting to add flow is a bad practice, but also because forgetting to add it resulted in linter bugs for imports, therefore creating issues with our CI.

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `eslint-plugin-flow-missing`:

```
$ npm install eslint-plugin-flow-missing --save-dev
```

**Note:** If you installed ESLint globally (using the `-g` flag) then you must also install `eslint-plugin-flow-missing` globally.

## Usage

Add `flow-missing` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["flow-missing"]
}
```

Then configure the rules you want to use under the rules section.

```json
{
  "rules": {
    "flow-missing/flow-missing": 2
  }
}
```

## Examples

The following examples are all valid :

```
// @flow
const test = 0;

...
```

```
/*
  author : Alburkerk
*/
// @flow
const test = 0;

...
```

The following examples are all NOT valid :

```
//@flow
const test = 0;

...
```

```
// @ flow
const test = 0;

...
```

```
const test = 0;

...
```
