# eslint-config

Preferring ES6, readability and low ambiguities. Extends the recommended ruleset
with some useful additions.

# How to use
- Install: `npm install @thomaschaplin/eslint-config --save-dev`
- Add it to your ESLint configuration:

```json
{
    "extends": ["@thomaschaplin"]
}
```

## Typescript
- Install the Typescript ESLint parser and plugin: `npm i @typescript-eslint/eslint-plugin @typescript-eslint/parser --save-dev`
- Add parser and plugin to your ESLint configuration:
```json
{
    "extends": ["@thomaschaplin"],
    "plugins": ["@typescript-eslint"],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": 6,
        "sourceType": "module",
        "ecmaFeatures": {
            "modules": true
        }
    }
}
```

- Currently, the TSLint parser has a few minor issues. For example, importing types triggers the rule `no-unused-vars` despite them being actually used as type annotations.

# Rules in detail
Environments: `node`, `es6`, `browser`

Unless noted, all rules are errors.

| Rule                                                       | Description                                                                                                                       |
|------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| [arrow-parens](https://eslint.org/docs/rules/arrow-parens) | Always wrap function arguments in brackets.                                                                                      |
| [brace-style](https://eslint.org/docs/rules/brace-style) | Curly brackets start after the keyword, not underneath.                                                                                      |
| [comma-dangle](https://eslint.org/docs/rules/comma-dangle) | Dangling commas in multiline objects, functions, arrays.                                                                                      |
| [complexity](https://eslint.org/docs/rules/complexity) | Maximum cyclomatic complexity of 3 to enforce highly maintaineable code (warning).                                                                                     |
| [curly](https://eslint.org/docs/rules/curly) | Curly brackets after if statements to avoid ambiguity when line breaks occur.                                                                                    |
| [eol-last](https://eslint.org/docs/rules/eol-last) | Empty line at the end of the file.                                                                                      |
| [func-call-spacing](https://eslint.org/docs/rules/func-call-spacing) | Brackets `()` to invoke a function have to stand right next to the function name.                                                                                      |
| [global-require](https://eslint.org/docs/rules/global-require) | `require()` statements should be at the top of the file (warning).                                                                                      |
| [linebreak-style](https://eslint.org/docs/rules/linebreak-style) | UNIX linebreaks.                                                                                      |
| [no-await-in-loop](https://eslint.org/docs/rules/no-await-in-loop) | Disallow `await` in loops (should use `Promise.all()` instead).                                                                                      |
| [no-default-export](https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-default-export.md) | Only allow named exports for increased consistency and clarity when importing modules. |
| [no-floating-decimal](https://eslint.org/docs/rules/no-floating-decimal) | Numbers have to be clear, i.e. `0.4` instead of `.4`.                                                                                      |
| [no-implicit-coercion](https://eslint.org/docs/rules/no-implicit-coercion) | Converting types from one to another have to be explicit.                                                                                      |
| [no-lone-blocks](https://eslint.org/docs/rules/no-lone-blocks) | No curly brackets unless necessary.                                                                           |
| [no-lonely-if](https://eslint.org/docs/rules/no-lonely-if) | Use `else if` instead of a lonely `if` wrapped inside an `else`.                                                                                       |
| [no-loop-func](https://eslint.org/docs/rules/no-loop-func) | Functions cannot be declared inside loops, they should be declared outside.                                                                                      |
| [no-template-curly-in-string](https://eslint.org/docs/rules/no-template-curly-in-string) | Avoid confusion whether a string is templated or not.                                                                                      |
| [no-throw-literal](https://eslint.org/docs/rules/no-throw-literal) | Throw errors explicitly, not just strings or values.                                                                                      |
| [no-var](https://eslint.org/docs/rules/no-var) | Use ES6 block-scoped`const` and `let`, never `var`.                                                                                      |
| [one-var](https://eslint.org/docs/rules/one-var) | Don't declare multiple variables in one line.                                                                                      |
| [prefer-const](https://eslint.org/docs/rules/prefer-const) | `let` should only be used where reassignment is necessary.                                                                                      |
| [prefer-promise-reject-errors](https://eslint.org/docs/rules/prefer-promise-reject-errors) | Promises should be `reject`ed with a clear error, not a simple value.                                                                                      |
| [prefer-spread](https://eslint.org/docs/rules/prefer-spread) | Use ES6 spread operator instead of difficult to understand ES5 `.apply()`.                                                                                      |
| [prefer-template](https://eslint.org/docs/rules/prefer-template) | Use template strings instead of string concatenation (warning).                                                                                      |
| [quotes](https://eslint.org/docs/rules/quotes) | Use unescaped double quotes.                                                                                      |
| [require-await](https://eslint.org/docs/rules/require-await) | `async` functions should perform an `await`, otherwise `async` keyword is unnecessary.                                                                                      |
| [semi](https://eslint.org/docs/rules/semi) | Don't use semicolons.                                                                                      |
| [yoda](https://eslint.org/docs/rules/yoda) | Don't use unintuitive conditions.                                                                                    |
