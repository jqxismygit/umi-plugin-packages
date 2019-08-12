<h1 align="center">umi-plugin-deploy-config</h1>

插件作用提取项目部署的配置到输出目录的根目录

* 输出配置文件如下
```
// config.js
(function() {
  // API地址
  window.baseURL = 'https://api.***.com';
  // 路由基本路径
  window.routerBase = "/";
  // 共有路径
  window.publicPath = "https://cdn.***.com/${project-name}/${env}/";
})();
```

* 输出Html文件如下
```
// 核心代码
<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="./config.js?t=1565598003"></script>
    <script>
      var bundleStyle = document.createElement('link');
      bundleStyle.rel = 'stylesheet';
      bundleStyle.href = window.publicPath + 'umi.daee5917.css';
      document.head.appendChild(bundleStyle);
    </script>
  </head>
  <body>
    <noscript>Sorry, we need js to run correctly!</noscript>
    <div id="root"></div>
    <script>
      var bundleScript = document.createElement('script');
      bundleScript.type = 'text/javascript';
      bundleScript.src = window.publicPath + 'umi.3abab410.js';
      document.body.appendChild(bundleScript);
    </script>
  </body>
</html>

```

