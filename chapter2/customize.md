## 自定义地图
&emsp;&emsp;首先，注册 成为高德地图开放平台的开发者，确保获取准确的key。然后，在[自定义地图平台](https://lbs.amap.com/dev/mapstyle/index) 进行创建、编辑、**发布** 后，取得 地图样式ID。
```
var map = new AMap.Map('container',{
    mapStyle: 'amap://styles/地图样式ID', //设置地图的显示样式
});
```
注意：
  
    完成编辑的自定义地图，需要点击“发布”，发布成功后然后进入到“使用与分享”页面获取地图样式的ID。

    如下原因可能会导致自定义地图没有效果：

    1、未填写Key，使用 JS API 的自定义地图服务，需要申请 web端（JS API）的 Key 进行配置。

    2、填写的 Key 与 styleid 不匹配，Key 与 styleid 需要是在同一账户下。

