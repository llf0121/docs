# JSSDK

微信 JSSDK 官方文档：https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421141115

## API

>  - `$app->jssdk->buildConfig(array $APIs, $debug = false, $beta = false, $json = true);` 获取JSSDK的配置数组，默认返回 JSON 字符串，当 `$json` 为 `false` 时返回数组，你可以直接使用到网页中。
>  - `$app->jssdk->setUrl($url)` 设置当前URL，如果不想用默认读取的URL，可以使用此方法手动设置，通常不需要。

示例：

我们可以生成js配置文件：

```js
<script src="http://res.wx.qq.com/open/js/jweixin-1.2.0.js" type="text/javascript" charset="utf-8"></script>
<script type="text/javascript" charset="utf-8">
    wx.config(<?php echo $app->jssdk->buildConfig(array('onMenuShareQQ', 'onMenuShareWeibo'), true) ?>);
</script>
```
结果如下：

1.2 版本：

> {warning} 官方即将废弃该版本，请不要再使用

```js
<script src="http://res.wx.qq.com/open/js/jweixin-1.2.0.js" type="text/javascript" charset="utf-8"></script>
<script type="text/javascript" charset="utf-8">
wx.config({
    debug: true,
    appId: 'wx3cf0f39249eb0e60',
    timestamp: 1430009304,
    nonceStr: 'qey94m021ik',
    signature: '4F76593A4245644FAE4E1BC940F6422A0C3EC03E',
    jsApiList: ['onMenuShareQQ', 'onMenuShareWeibo']
});
</script>
```

或者最新的 1.4 版本：

```js
<script src="http://res.wx.qq.com/open/js/jweixin-1.4.0.js" type="text/javascript" charset="utf-8"></script>
<script type="text/javascript" charset="utf-8">
wx.config({
    debug: true,
    appId: 'wx3cf0f39249eb0e60',
    timestamp: 1430009304,
    nonceStr: 'qey94m021ik',
    signature: '4F76593A4245644FAE4E1BC940F6422A0C3EC03E',
    jsApiList: ['updateAppMessageShareData', 'updateTimelineShareData']
});
</script>
```

