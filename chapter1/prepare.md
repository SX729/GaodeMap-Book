## 准备工作
### 注册账号并申请Key

1. 首先，注册开发者账号，成为高德开放平台开发者

2. 登陆之后，在进入「应用管理」 页面「创建新应用」

3. 为应用添加 Key，「服务平台」一项请选择「 Web 端 ( JSAPI ) 」


### 准备页面
&emsp;&emsp;在页面添加 JS API 的入口脚本标签，并将其中「您申请的key值」替换为刚刚申请的 key；

```
  <script type="text/javascript" src="https://webapi.amap.com/maps?v=1.4.15&key=您申请的key值"></script> 
```
注意：进行移动端开发时，请在head内添加viewport设置，以达到最佳的绘制性能
```
  <meta name="viewport" content="initial-scale=1.0, user-scalable=no"> 
```