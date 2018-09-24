# eslint

Instructions for adding Taskful lint standards to a project:

```npm install --save-dev eslint-config-taskful eslint lint-staged pre-commit```

Add these objects to the package.json:

```
"scripts": {
  "lint-staged": "lint-staged"
},
"lint-staged": {
  "*.js": "eslint"
},
"pre-commit": "lint-staged",
```
This will setup a pre-commit hook that will lint all staged files with the `js` ext.

Add an .eslintrc file in project root with format:

```
{
  "extends": "taskful",
  "root": true,
  "globals": {},
  "rules": {},
}
```
Globals is where global variables can be exposed to eslint ex. `"document": true` will expose the document variable that is present in the browser so that code references to it will not be flagged.
Rules is where project specific rules and overrides are declared ex. `"jsx-a11y/no-static-element-interactions": 0` disables jsx-a11y's static element interaction rule.
