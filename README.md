# Gusals API: Clean Architecture with .NET Core

## Solution Set up

* add [.gitignore](https://www.toptal.com/developers/gitignore)

* dotnet tool install

    ```bash
    > dotnet new tool-manifest
    ```

* add .editorconfig

  * [EditorConfig](https://editorconfig.org/)

  * [Code style rule options](https://docs.microsoft.com/ko-kr/dotnet/fundamentals/code-analysis/code-style-rule-options)

* create package.json

    ```bash
    > npm init
    ```

  * add husky, lint-staged

  ```bash
  # npm
  > npm install husky lint-staged --save-dev
  
  # yarn
  > yarn add husky lint-staged --dev
  ```

  * edit package.json

  ```json
  ...,
  "husky": {
      "hooks": {
          "pre-commit": "lint-staged -r"
      }
    }
  ```

  * add .lintstagedrc.js

  ```js
  module.exports = {
      '*.cs': filenames => [
          `dotnet dotnet-format --files ${filenames.join(',')}`,
          `git add ${filenames.join(' ')}`
      ]
  }
  ```

* package install

```bash
# npm
> npm install

# yarn
> yarn install
```
