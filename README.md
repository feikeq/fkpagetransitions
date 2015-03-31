#FKPageTransitions v1.2
##响应式jQuery插件滑动翻页组件

###什么要使用这个滑块？
* 完全适应任何设备屏幕
* 水平，垂直，和淡入等37种翻页效果
* 幻灯片可以包含图像，视频，HTML内容，或各种动画元素。
* 充分回调API和公共方法
* 小体积，自定义样式，简单的使用代码
* 支持浏览器Firefox，Safari，Chrome，：iOS，Android，IE9 +
* 丰富的配置选项

废客联邦官网访问地址：

[http://fk68.net](http://fk68.net)

作者：废客泉 - [https://github.com/feikeq/fkpagetransitions](https://github.com/feikeq/fkpagetransitions)

[预览FKPageTransitions效果](http://htmlpreview.github.io/?https://github.com/feikeq/fkpagetransitions/blob/master/demo.htm)

###微博
新浪微博 - http://feikeq.cn

让我们继续吧！

##使用方法

###1: 载入所需的文件

要先引入jQuery库需要包括（你可以去它官网下载）。其次，从本网站下载fkpagetransitions.css和fkpagetransitions.min.js文件。

```html
<!-- jQuery library -->
<script src="jquery/jquery.min.js"></script>
<!-- FKPageTransitions Javascript file -->
<script src="/js/fkpagetransitions.min.js"></script>
<!-- FKPageTransitions CSS file -->
<link href="/css/fkpagetransitions.css" rel="stylesheet" />
```

###2: 创建HTML代码

创建一个`<ul class="test">` 元素, 一个` <li> `为一个幻灯片。幻灯片可以包含图像，视频，或任何其他HTML内容！

```html
<ul class="test">
  <li><img src="/images/pic1.jpg" /></li>
  <li><img src="/images/pic2.jpg" /></li>
  <li><img src="/images/pic3.jpg" /></li>
  <li><img src="/images/pic4.jpg" /></li>
</ul>
```

###3: 调用组件

调用.FKPageTransitions() 在 `<ul class="test">`元素上

```javascript
$(document).ready(function(){
  $('.test').FKPageTransitions();
});
```

##配置选项

###基本设置

**mode**
幻灯片之间的过渡效果
```
default: 0
options: [0-37]
单数为适合左右操作，双数适合上下操作
			其中0、31、32、34、36、37可左右上下通用。
			------------------------------------------------
			0：淡入翻页(适合左右和上下操作)
			1、2：简单位移翻页
			3、4：新页位移入场旧页变暗位置不动
			5、6：新旧页同时位移旧页变暗
			7、8：新页位移入场旧页浮动位移
			9、10：新页位移入场旧页变小
			11、12：新页位移入场旧页揭下和9、10差不多
			13、14：旧页位移新页放大入场
			15、16：新页位移入场旧页顶下去
			17、18：新旧页同时面对面翻页入场和出场
			19、20：新旧页像盒子一样转动
			21、22：新旧页像盒子一样展开
			23、24：新旧页像在盒子里一样转动
			25、26：新旧页像盒子一样转动视角由小大变小再由小变大
			27、28：新旧页立体间飞行位移
			29、30：新页缩小和旧变大页翻转交错入场
			31：新页和旧页一起淡入效果同时变小(适合左右和上下操作)
			32：新页和旧页一起淡入效果同时变大(适合左右和上下操作)
			33：新旧页同时面对面翻页入场和出场周时变小与24差不多(适合左右)
			34:旧页固定顶角再掉落新页放大入场(适合左右和上下操作)
			35：旧页缩小移出新页移出放大入场(适合左右)
			36：新页缩小旧页变大交错入场(适合左右和上下操作)
			37：新页缩小和旧变大页旋转交错入场(适合左右和上下操作)
```

**speed**
滑过渡时间（毫秒）
```
default: null
options: integer
```


**startSlide**
启动幻灯片索引（从零开始）
```
default: 0
options: integer
```
 
**slideSelector**
元作为幻灯片（例如<code>'div.slide'</code>。<br>注：默认情况下，bxslider将使用滑块元素的所有直接的孩子
```
default: ''
options: jQuery selector
```

**infiniteLoop**
如果为 <code>true</code>,单击“下一步”在最后一张幻灯片将过渡到第一张幻灯片，反之亦然
```
default: true
options: boolean (true / false)
```

**easing**
过程中使用的转换 "easing" 使用CSS转换, 值请参考 <code>transition-timing-function</code> 的参数说明
 
```
default: null
options: if using CSS: 'linear', 'ease', 'ease-in', 'ease-out', 'ease-in-out'..
```

**slideZIndex**
初始z-index数
```
default: 50
options: integer
```


**responsive**
启用或禁用自动调整滑块。如果你需要使用固定宽度的滑块。
```
default: true
options: boolean (true /false)
```

**wrapperClass**
翻页框架类名。防止有样式与FKPageTransitions冲突。
```
default: 'fk-page-wrapper'
options: string
```

**mouseWheel**
是否支持滚轮
```
default: false
options: boolean (true / false)
```

**wheelThreshold**
鼠标的灵敏度阀值
```
default: 2
options: integer
```


**swipeThreshold**
触摸灵敏度阀值
```
default: 50
options: integer
```

**preventDefaultSwipeX**
如果<code>true</code>，触摸屏沿x轴为手指操作(如果为false并preventDefaultSwipeY也为falase那么不响应touch事件)
```
default: true
options: boolean (true / false)
```

**preventDefaultSwipeY**
如果<code>true</code>，触摸屏沿y轴为手指操作(如果为false并preventDefaultSwipeY也为falase那么不响应touch事件)
```
default: false
options: boolean (true / false)
```
 

**pagerunstat**
如果<code>true</code>，在翻页动画进行时禁止页面内元素动画渲染
```
default: false
options: boolean (true / false)
```




###回调方法

**onSliderLoad**
加载完成时回调
```
default: function(){}
options: function(currentIndex){ // 写你的代码 }
参数:
 currentindex：当前幻灯片的元素的索引
```

**onSliderResize**
窗口发生变化时回调,前提[responsive=true]
```
default: function(){}
options: function(currentIndex){ // 写你的代码 }
参数:
 currentindex：当前幻灯片的元素的索引
```

**onSlideBefore**
在每动画过渡开始前回调
```
default: function(){}
options: function(newIndex,oldIndex,newElement,oldElement){ // 写你的代码 }
参数:
  newIndex:当前页码
  oldIndex:之前页码
  newElement:当前的jQuery元素
  oldElement:之前的jQuery元素
```

**onSlideAfter**
在每动画过渡结束后回调
```
default: function(){}
options: function(newIndex,oldIndex,newElement,oldElement){ // 写你的代码 }
参数:
  newIndex:当前页码
  oldIndex:之前页码
  newElement:当前的jQuery元素
  oldElement:之前的jQuery元素
```

**onSlideNext**
执行下一页时回调
```
default: function(){}
options: function(newIndex,oldIndex,newElement,oldElement){ // 写你的代码 }
参数:
  newIndex:当前页码
  oldIndex:之前页码
  newElement:当前的jQuery元素
  oldElement:之前的jQuery元素
```

**onSlidePrev**
执行上一页时回调
```
default: function(){}
options: function(newIndex,oldIndex,newElement,oldElement){ // 写你的代码 }
参数:
  newIndex:当前页码
  oldIndex:之前页码
  newElement:当前的jQuery元素
  oldElement:之前的jQuery元素
```

###公共方法调用

**goToSlide**
执行一个幻灯片过渡到提供的幻灯片的索引（从零开始）
```
例:
slider = $('.test').FKPageTransitions();
slider.goToSlide(3);
```

**goToNextSlide**
执行“下一步”幻灯片过渡
```
例:
slider = $('.test').FKPageTransitions();
slider.goToNextSlide();
```

**goToPrevSlide**
执行“上一页”的幻灯片过渡
```
例:
slider = $('.test').FKPageTransitions();
slider.goToPrevSlide();
```


**getCurrentSlide**
返回当前活动的幻灯片
```
例:
slider = $('.test').FKPageTransitions();
var current = slider.getCurrentSlide();
```

**getSlideCount**
返回在滑块总幻灯片的数目
```
例:
slider = $('.test').FKPageTransitions();
var slideQty = slider.getSlideCount();
```


**setSlideMode**
动态设置新的翻页效果（0-37）
```
例:
slider = $('.test').FKPageTransitions();
slider.setSlideMode(25);
```

**reloadSlider**
重新装入滑块。
```
例:
slider = $('.test').FKPageTransitions();
slider.reloadSlider();
```
 

## 更新日志
### Version 1.2 (2015-03-31)
* 在翻页动画执行前停止要操作页的所有CSS动画渲染(pagerunstat=true)，翻页动画结束后再继续播放CSS动画渲染,以免在手机上为节省性能导致翻页无效果
* 回调方法添加上个元素对象prev_obj



### Version 1.1
* 设置X和Y为flash不响应touch事件


### Version 1.0
* 支持鼠标
* 支持响应式


废客联邦
自由无止境.自由的引领.自由的联盟.自由让你我腾飞!为了同一目标而奋斗，为了同一信念而聚一堂，为了网络事业的明天而烈火青春.
