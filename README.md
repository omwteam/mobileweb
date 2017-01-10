# 移动web页面模板及注意事项

```
<!DOCTYPE html>
<html>
<head>
    <title>页面标题</title>
    <meta charset="utf-8">
    <!--设定缩放比，是否可缩放-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <!--安全策略设置-->
    <meta http-equiv="Content-Security-Policy" content="default-src *;frame-src gap://* jsbridge://* wvjbscheme://*;style-src 'self' http://*.okii.com https://*.okii.com 'unsafe-inline'; script-src 'unsafe-inline' 'unsafe-eval' http://*.okii.com http://www.omwteam.com https://*.omwteam.com https://www.omwteam.com;">
    <!---->
    <meta name="apple-mobile-web-app-capable" content="yes" />
    <!--设置导航栏的风格-->

    <meta name="apple-mobile-web-app-status-bar-style" content="black" />
    <!--避免IOS上数字和邮箱可操作-->
    <meta name="format-detection" content="telephone=no, email=no" />
    <!--设置缓存处理方式-->
    <meta http-equiv="Cache-Control" content="no-cache">
    <link rel="shortcut icon" href="favicon.ico">
    <link rel="stylesheet" href="http://cdn.omwteam.com/omreset/omreset.min.css">

</head>
<body>
<div id="app">

</div>
<!-- built files will be auto injected -->

<script src="//cdn.bootcss.com/jquery/3.1.1/jquery.slim.min.js"></script>
</body>
</html>


```

## 安全策略设置

```
<meta http-equiv="Content-Security-Policy" content="default-src *;frame-src gap://* jsbridge://* wvjbscheme://*;style-src 'self' http://*.okii.com https://*.okii.com 'unsafe-inline'; script-src 'unsafe-inline' 'unsafe-eval' http://*.okii.com http://www.kuwo.cn https://*.okii.com https://www.kuwo.cn;">
```

[详细参考](https://imququ.com/post/content-security-policy-reference.html)

## 设置viewport
```
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />

  强制让文档与设备的宽度保持 1:1 ；
    文档最大的宽度比列是1.0（ initial-scale 初始刻度值和 maximum-scale 最大刻度值）；
    user-scalable 定义用户是否可以手动缩放（ no 为不缩放），使页面固定设备上面的大小；
    注意：实际测试中发现，有些安卓系统自带的浏览器并不支持这一条规则，能够对页面进行放大，一旦放大响应的 box 也随之放大，导致页面出现错乱问题，解决方法：定义页面的最小宽度
    
body {
    min-width: 320px;
}
```

## name 属性的 format-detection 值（忽略页面中的数字识别为电话号码）
  

```
<meta name="format-detection" content="telephone=no, email=no" />
```

## name 属性的 apple-mobile-web-app-capable 值（网站开启对 web app 程序的支持）


```
<meta name="apple-mobile-web-app-capable" content="yes" />
```

## name 属性的 apple-mobile-web-app-status-bar-style 值（改变顶部状态条的颜色）


```
<meta name="apple-mobile-web-app-status-bar-style" content="black" />

在 web app 应用下状态条（屏幕顶部条）的颜色；
默认值为 default（白色），可以定为 black（黑色）和 black-translucent（灰色半透明）；
```
## 设置页面ico图标


```
  <link rel="shortcut icon" href="favicon.ico">
```


