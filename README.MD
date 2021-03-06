#pl
pl是一个基于CSS3`@media`特性实现的、轻量级的、横竖屏检测实用库，它让orientation detection更加可靠，更加easy。
#### 效果测试
![qrcode](qrcode.png)
### usage
将`pl`脚本（文件）引入`<head></head>`节点中。**注意**：  *将其放置在样式文件之后(保证不影响html的font-family的设置)*
```xml
<head>
  <meta charset="utf-8">
  <link rel="stylesheet" href="pl.css" type="text/css">
  <!-- 引入pl文件 -->
  <script type="text/javascript" src="js/library/pl.js"></script>
</head>
```
对需要检测横竖屏的地方，调用`pl.on(fn)`
```js
pl.on(function(event){
 if(event.current === 'portrait|landscape'){
 	// do something……
 } else {
 	// do something……
 }
});
```
`pl.on(fn)`的参数必须是`function`, 可以调用多次。

### API
##### pl.on(fn)
`fn`: function类型，该函数会在横竖屏发生变化时执行。同时会传递一个参数event(可以随意命名)给该函数，event参数等于`pl.orientation`
```js
event:{
  font: 'font-family',//初始化html的`font-family`
  init: 'portrait|landscape', //初始化时，横竖屏的状态
  current: 'portrait|landscape'//当前横竖屏的状态
}
```
注意：可以多次调用pl.on()函数。

```js
pl.on(function(event){
 if(event.current === 'portrait|landscape'){
 	// do something……
 } else {
 	// do something……
 }
});
```
##### pl.orientation
```js
pl.orientation:{
  font: 'font-family',//初始化html的`font-family`
  init: 'portrait|landscape', //初始化时，横竖屏的状态
  current: 'portrait|landscape'//当前横竖屏的状态
}
```
##### pl.event
订阅与发布事件模式
```js
pl.event.listen: 用于订阅特定的事件
pl.event.trigger：用于触发特定的事件
pl.event.remove: 用于删除特定的事件
```

### License
**pl.js** is covered by the MIT License.
