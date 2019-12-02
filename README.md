```js
{
  "name": "telescope",
  "version": "0.0.1",
  "scripts": {
    "prettier": "prettier --write \"./**/*.{md,json,html,css,js,yml}\"",
  },
  "husky": {
    "hooks": {
      "pre-commit": "pretty-quick --staged"
    }
  },
  // ...
}

```
