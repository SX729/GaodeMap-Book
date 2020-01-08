## 原生创建方式
### 地图容器
&emsp;&emsp;添加div标签作为地图容器，同时为该div指定id属性；
```
  <div id="container"></div> 
```
或者使用react的ref锁定容器节点：
```
  <div style={{ width: '100%', height: '100%' }} ref="container" />
  // 获取：let container = this.refs.container
```
注意：地图容器要有高度和宽度，否则无法显示出来。
### 创建地图
```
  window.onLoad  = function(){
    var map = new AMap.Map('container');
  }
```
或者在react的componentDidMount生命周期中
```
  componentDidMount() {
    let content = this.refs.container
    this.Amap = new window.AMap.Map(content, {})
```
注意：
  如果写成 ```new AMap.Map```, 则react下找不到原生高德地图AMap，可以在上一行写：```// eslint-disable-next-line```，告诉eslint：注释下面这一行别管，或者写成：```new window.AMap.Map```