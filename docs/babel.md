# Babel 配置

这个模板用 [`babel-preset-env`](https://www.npmjs.com/package/babel-preset-env) 为了配置 babel。 关于这个你可以阅读更多 - http://2ality.com/2017/02/babel-preset-env.html.

> 你需要基于你的目标浏览器或者运行时环境，一个将ES2015+编译到ES5的babel预设值自动决定了babel的插件和polyfills

利用 [`browserslist`](https://github.com/ai/browserslist)去解析这些信息, 所以我们可以利用所有 [valid query format supported by `browserslist`](https://github.com/ai/browserslist#queries).

但是这里是一个警告。 `browserslist` 命令定义目标在一个公共地方像 `package.json` 或者在一个 `.browserslistrc` 配置文件。这允许工具像 [`autoprefixer`](https://github.com/postcss/autoprefixer) 和 [`eslint-plugin-compat`](https://github.com/amilajack/eslint-plugin-compat) 去分享配置。这个模板 `browserslist` 配置在`package.json`:

```json
{
  "...": "...",
  "browserslist": [
    "> 1%",
    "last 2 versions",
    "not ie <= 8"
  ]
}
```

但是最新最稳定的版本 `babel-preset-env`, `v1.6.1` 不支持从 `package.json`中加载。 所以在`.babelrc` 中目标是重复的。如果你希望改变你的目标环境， 请确保更新所有的 `package.json` 和 `.babelrc`。注意这个问题再bata版本中已经被解决了([`@babel/preset-env@7.0.0-beta.34`](https://github.com/babel/babel/tree/master/packages/babel-preset-env)) 并且模板将在测试结束后进行更新。
