# 项目结构

``` bash
.
├── build/                      # webpack 配置文件
│   └── ...
├── config/
│   ├── index.js                # 主项目配置
│   └── ...
├── src/
│   ├── main.js                 # app 文件
│   ├── App.vue                 # 主app组件
│   ├── components/             # ui组件
│   │   └── ...
│   └── assets/                 # module assets (processed by webpack)
│       └── ...
├── static/                     # 纯静态资产(直接复制)
├── test/
│   └── unit/                   # 单元测试
│   │   ├── specs/              # 测试规范文件
│   │   ├── eslintrc            # eslint的配置文件，仅为单元测试添加额外设置
│   │   ├── index.js            # 测试构建条目文件
│   │   ├── jest.conf.js        # 用jest做单元测试的配置文件
│   │   ├── karma.conf.js       # 在对单元测试使用Karma时测试运行器配置文件
│   │   └── setup.js            # 在Jest运行单元测试之前运行的文件
│   └── e2e/                    # e2e 测试
│   │   ├── specs/              # 测试规范文件
│   │   ├── custom-assertions/  # e2e测试的自定义断言
│   │   ├── runner.js           # 测试运行时脚本
│   │   └── nightwatch.conf.js  # 测试运行时配置文件
├── .babelrc                    # babel 配置
├── .editorconfig               # 编辑器的缩进、空格/tabs和类似设置
├── .eslintrc.js                # eslint 配置
├── .eslintignore               # eslint ignore 规则
├── .gitignore                  # sensible defaults for gitignore
├── .postcssrc.js               # postcss config
├── index.html                  # index.html template
├── package.json                # build scripts and dependencies
└── README.md                   # Default README file
```

### `build/`

此目录包含开发服务器和生产webpack构建的实际配置。 正常的你不需要碰这些文件除非你想要去自定义, 在这种情况下，你应该看看 `build/webpack.base.conf.js`.

### `config/index.js`

这是为构建设置公开一些最常见配置选项的主要配置文件。为了更多的信息，看 [API Proxying During Development](proxy.md) 和 [Integrating with Backend Framework](backend.md) .

### `src/`

这是您的大多数应用程序代码所在的位置。如何构造这个目录中的所有内容很大程度上取决于您;如果你正在使用Vuex，你可以咨询 [recommendations for Vuex applications](http://vuex.vuejs.org/en/structure.html).

### `static/`

这个目录是一个转义窗口，用于存放你不想用Webpack处理的静态资源。它们将被直接复制到生成webpack-built资产的同一个目录中。

为了更多的信息，看[Handling Static Assets](static.md)。

### `test/unit`

包含单元测试相关文件。为了更多的信息，看[Unit Testing](unit.md) 。

### `test/e2e`

包含e2e测试相关文件。为了更多的信息，看[End-to-end Testing](e2e.md) 。

### `index.html`

这是我们单页面应用的 **模板** `index.html`。 在开发和构建期间，Webpack将生成资产，这些生成资产的url将自动注入到这个模板中，以呈现最终的HTML。

### `package.json`

NPM包元文件，包含所有构建依赖项和和[build commands](commands.md).
