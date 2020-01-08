## 覆盖物事件
覆盖物的事件和 DOM 事件类似：[覆盖物事件](https://lbs.amap.com/api/javascript-api/guide/events/map_overlay)
可以有两种写法：
```
  marker.on('click', function (e) {
    console.log(e)
    console.log(e.target.getExtData())
  })
```
```
  window.AMap.event.addListener(marker, 'click',  function (e) {
    console.log(e.target.getExtData())
  })
```
其中getExtData() 用于获取标记点上的自定义属性。
解绑事件：
```
map.off('click', clickHandler);
```