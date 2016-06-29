How to use ESLint to check js code
==================================

```
npm install -g eslint

cd js
npm install
eslint src --rulesdir ./node_modules/eslint-rules/
```

You will see all the issues eslint found in the console. For now, it's:

```
 js git:(master) eslint src --rulesdir ./node_modules/eslint-rules/

/Users/twer/workspace/eslint-checking-demo/js/src/book.js
  4:3   error  Expected indentation of 4 space characters but found 2  indent
  9:5   error  "str" is defined but never used                         no-unused-vars
  9:11  error  Unexpected string concatenation                         prefer-template

/Users/twer/workspace/eslint-checking-demo/js/src/calculator.js
   9:1   warning  commented out code "function hello() {}" (3 lines)  no-commented-out-code
  20:67  error    Missing semicolon                                   semi
  24:36  error    Function 'anonymous' has a complexity of 5          complexity

/Users/twer/workspace/eslint-checking-demo/js/src/cart.js
   4:22  error  Infix operators must be spaced                          space-infix-ops
   5:23  error  Infix operators must be spaced                          space-infix-ops
  11:27  error  Function 'anonymous' has a complexity of 5              complexity
  13:5   error  Expected indentation of 8 space characters but found 4  indent

/Users/twer/workspace/eslint-checking-demo/js/src/packager.js
   0:0   error  file line count 65 exceeded line limit 50                        no-long-files
  12:38  error  This function has too many statements (7). Maximum allowed is 6  max-statements
  43:34  error  Function 'anonymous' has a complexity of 5                       complexity

✖ 13 problems (12 errors, 1 warning)
```

Where are the rules from
------------------------

1. [eslint built-in rules](https://github.com/eslint/eslint/blob/master/conf/eslint.json)
2. https://github.com/bahmutov/eslint-rules

Where are the rules used when checking
--------------------------------------

`js/.eslintrc`, including all the used rules

Note: the first argument for each rule means the level

- `0`: disable
- `1`: warning
- `2`: error

e.g.

```
"indent": [2, 4]
```

The first `2` means `error`, and the second `4` means `4 spaces`

How to generate basic rules file for eslint
-------------------------------------------

`eslint --init`

Follow the instructions, finally there is an `.eslintrc` file generated.

(I have already generated one in `js` directory)
