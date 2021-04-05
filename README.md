# Pre-commit checks with Husky

```
npx husky-init
```

```
yarn add -D lint-staged prettier
```


add lint-staged to package.json

```
"lint-staged": {
    "**/*.{js,jsx,ts,tsx}": [
      "yarn eslint",
      "yarn prettier --write",
      "yarn test --watchAll=false --findRelatedTests --bail"
    ]
  }

```

add to .husky/pre-commit

```
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

yarn tsc
yarn lint-staged


```

Run yarn when use git pull and check there is new libs
```
npx husky add .husky/post-merge 'yarn'

```