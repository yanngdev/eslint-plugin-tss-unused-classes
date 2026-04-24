# Detect unused tss-react classes

This eslint plugin lets you detect unused [tss-react](https://tss-react.dev) classes:

https://user-images.githubusercontent.com/6702424/167231369-4eaeb5b2-bb39-4647-9911-086572c5e212.mov

# Usage

1. Add the dependency:
```sh
yarn add --dev eslint-plugin-tss-unused-classes
```

2. Enable it in your ESLint config

**Case 1**: You are in a [`create-react-app`](https://create-react-app.dev/) project:  
Edit your `package.json`:  

```jsonc
{
  //...
  "eslintConfig": {
    "plugins": [
      //...
      "tss-unused-classes"
    ],
    "rules": {
      "tss-unused-classes/unused-classes": "warn"
    }
  },
  //...
}
```
[Example project](https://github.com/InseeFrLab/onyxia-web)

**Case 2**: You have a legacy ESLint config (ESLint < 9, `.eslintrc.js`):  
Edit your `.eslintrc.js` file:  
```js
module.exports = {
  // ...
  plugins: [
    // ...
    'tss-unused-classes'
  ],
  rules: {
    // ...
    'tss-unused-classes/unused-classes': 'warn'
  }
}
```
[Example project](https://github.com/InseeFrLab/onyxia-ui)

**Case 3**: You are using the flat config (ESLint 9+, `eslint.config.js` or `eslint.config.mjs`):  
```js
import tssUnusedClasses from 'eslint-plugin-tss-unused-classes';

export default [
  // ...
  {
    plugins: {
      'tss-unused-classes': tssUnusedClasses
    },
    rules: {
      'tss-unused-classes/unused-classes': 'warn'
    }
  }
];
```

Or using CommonJS:
```js
const tssUnusedClasses = require('eslint-plugin-tss-unused-classes');

module.exports = [
  // ...
  {
    plugins: {
      'tss-unused-classes': tssUnusedClasses
    },
    rules: {
      'tss-unused-classes/unused-classes': 'warn'
    }
  }
];
```

> **Note:** ESLint 10 also uses the flat config format. The `eslint.config.js` examples above are valid for both ESLint 9 and 10.

## Disabling warnings

In case of false positive, disable the warning:

- For the next line: `// eslint-disable-next-line tss-unused-classes/unused-classes`
- For the entire file: `/* eslint-disable tss-unused-classes/unused-classes */`
