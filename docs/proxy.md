# 在开发期间的api代理

在这个模板和一个已经存在的后端集合时，一个常见的需求就是当使用dev服务器去访问后端api。为了实现那个，我们可以同时运行开发服务器和api后端，并且让开发服务器去代理所有api请求到真实的后端地址。

为了管理代理规则，编辑 `dev.proxyTable` 选项在 `config/index.js`。这个开发服务器正使用 [http-proxy-middleware](https://github.com/chimurai/http-proxy-middleware) 作为代理，所以你需要阅读其相关详细使用文档。但是这是一个简单例子：
``` js
// config/index.js
module.exports = {
  // ...
  dev: {
    proxyTable: {
      // proxy all requests starting with /api to jsonplaceholder
      '/api': {
        target: 'http://jsonplaceholder.typicode.com',
        changeOrigin: true,
        pathRewrite: {
          '^/api': ''
        }
      }
    }
  }
}
```

The above example will proxy the request `/api/posts/1` to `http://jsonplaceholder.typicode.com/posts/1`.

## URL Matching

In addition to static urls you can also use glob patterns to match URLs, e.g. `/api/**`. See [Context Matching](https://github.com/chimurai/http-proxy-middleware#context-matching) for more details. In addition, you can provide a `filter` option that can be a custom function to determine whether a request should be proxied:

``` js
proxyTable: {
  '**': {
    target: 'http://jsonplaceholder.typicode.com',
    filter: function (pathname, req) {
      return pathname.match('^/api') && req.method === 'GET'
    }
  }
}
```
