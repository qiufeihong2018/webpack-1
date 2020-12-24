# Linter配置

这个模板使用 [ESLint](https://eslint.org/) 作为 linter, 并且使用 [Standard](https://github.com/feross/standard/blob/master/RULES.md) 预设一些小的自定义配置。

## eslint-plugin-vue

我们同样可以添加 [eslint-plugin-vue](https://github.com/vuejs/eslint-plugin-vue)， 它提供一大堆有用的规则去书写一致的vue组件-它也可以检测模板！

你也可以找到所有有用规则的概述在 [github](https://github.com/vuejs/eslint-plugin-vue#gear-configs)中。 我们选择添加 `essential` 配置，但是我们推荐你熟悉了他们之后去改写 `strongly-recommended` 或者 `recommended` 规则集。
## 自定义

如果你使用默认的检测规则不开心，你可以自定义选项：

1. 在 `.eslintrc.js` 中覆盖单个规则。例如，你可以添加以下规则来强制分号而不是省略它们:

  ``` js
  // .eslintrc.js
  "semi": [2, "always"]
  ```

2. 例如，在生成项目时选择一个不同的ESLint预置 [eslint-config-airbnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb)。

3. 在生成项目时为ESLint预设选择"none"并定义你自己的规则。为了获取更多信息，请看 [ESLint documentation](https://eslint.org/docs/rules/) 。

## 解决检测错误

你可以运行以下命令，让eslint修复它发现的任何错误(如果它能修复的话——并不是所有的错误都像这样可以修复):

```
npm run lint -- --fix
```

*（中间的 `--` 是必要的，以确保 `--fix` 项被传递给  `eslint`，而不是 `npm`。使用yarn时可省略）*


