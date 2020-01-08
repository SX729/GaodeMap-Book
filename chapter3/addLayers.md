## 添加图层
[自有数据图层](https://lbs.amap.com/api/javascript-api/example/selflayer/imagelayer)：
```
  let Layer = new AMap.ImageLayer({
    url: 'static/images/image01.png',
    bounds: new AMap.Bounds(
      [117.204867, 39.084839],   //左下角
      [117.206208, 39.08633]    //右上角
    ),
    zooms: [15, 18]
  });
  map.add(Layer)
  //map.setLayers(Layer);
```
也可以设置官方图层
```
  // 构造官方卫星、路网图层
  var layers =  [
      new AMap.TileLayer.Satellite(),
      new AMap.TileLayer.RoadNet()
  ]
  // 地图上设置图层
  map.setLayers(layers);
```
## 获取图层
```
  map.getLayers()
```

## 移除图层
```
  map.remove(layer1);
```