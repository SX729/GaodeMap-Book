## 添加覆盖物

&emsp;&emsp;覆盖物有多种类型，包括点标记、矢量图形、信息窗体等，文档地址见：[mark 类型、属性、方法](https://lbs.amap.com/api/javascript-api/reference/overlay#icon)，现以添加自定义覆盖物为例进行说明：

```
  var marker = new window.AMap.Marker({
    // icon: require('@assets/images/u36.png'),
    content: `<div><img src="static/images/u36.png"/></div>`,
    extData: {
      'id': 1
    },
    position: [117.205362, 39.085439],
    offset: new window.AMap.Pixel(-24, -40),
    label: {
      content: '<div>天津利华大酒店</div>',
      direction: 'bottom',
      offset: new window.AMap.Pixel(24, 40),
    }
  });
  this.Amap.add(marker);
```

还可以用以下方式添加：

```
  marker.setMap(this.Amap);//在地图上添加点
  marker.setTitle('罗家庙站'); //设置鼠标划过点标记显示的文字提示
```

说明：

- 3D 地图用自己的图片作为 marker 点标记，定位会出现位置不对的问题，所以设置 offset 偏移量。
- 可以在项目 static 文件夹下新建图片文件夹，然后将所有的静态资源都放入这个文件夹中，这样打包的时候，依旧能找到图片路径，并且图片是独立打包称文件夹。
- content 设置点标记显示内容，可以是 HTML 要素字符串或者 HTML DOM 对象。content 有效时，icon 属性将被覆盖。
- extData 用户自定义属性，支持 JavaScript API 任意数据类型

## 获取覆盖物

&emsp;&emsp;可以使用 getAllOverlays(type)方法获取已经添加的覆盖物。其中 type 参数类型包括 marker、circle、polyline、polygon，缺省是返回以上所有类型所有覆盖物。

```
// 获取已经添加的覆盖物
map.getAllOverlays();

// 获取已经添加的marker
map.getAllOverlays('marker');
```

## 移除覆盖物

&emsp;&emsp;使用 remove 方法移除覆盖物，参数可以为单个覆盖物对象，也可以是一个包括多个覆盖物的数组

```
// 单独移除点标记
map.remove(marker);
// 同时移除点标记和矢量圆形
map.remove([marker,circle]);

// 使用clearMap方法删除所有覆盖物
map.clearMap();
```
