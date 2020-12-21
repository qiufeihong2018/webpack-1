# 构建命令

所有的构建命令都是通过 [NPM脚本](https://docs.npmjs.com/misc/scripts)执行的。

### `npm run dev`

> 开启一个Node.js本地开发服务器。为了获得更多信息，看 [API Proxying During Development](proxy.md)。

- Webpack + `vue-loader` 为vue单页面文件
- 状态保护热重载
- 状态保留编译错误覆盖
- 用 ESLint Lint-on-save 
- 源映射

### `npm run build`

> 为生产环境构建静态文件。 为了获得更多信息，看 [Integrating with Backend Framework](backend.md)。

- 用[UglifyJS v3](https://github.com/mishoo/UglifyJS2/tree/harmony)压缩javascript。
- 用[html-minifier](https://github.com/kangax/html-minifier)压缩html。
- 用[cssnano](https://github.com/ben-eb/cssnano)将CSS的所有组件提取并压缩成一个单一的文件。
- 为了高效的长期缓存，用版本哈希去编译所有的静态资源文件，并且生产环境的 `index.html` 自动生成正确的url到这些生成的静态文件。

### `npm run unit`

> 用[Jest](https://facebook.github.io/jest/docs/getting-started.html)在JSDOM中运行单元测试。 为了获得更多信息，看 [Unit Testing](unit.md) 。

- 支持 ES2015+ 在测试文件中。
- 简单的 [mocking](https://facebook.github.io/jest/docs/mock-functions.html)。

### `npm run e2e`

> 用 [Nightwatch](http://nightwatchjs.org/)运行端对端测试。 为了获得更多信息，看 [End-to-end Testing](e2e.md) 。

- 在多个浏览器中并行运行测试。
- 用一个命令开箱即用：
  - Selenium and chromedriver 依赖自动处理。
  - 自动生成Selenium服务器。

### `npm run lint`

> 运行 eslint和支持各种 linting 错误在你的代码中。 看 [Linter Configuration](linter.md)
