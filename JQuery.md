# JQuery

## 什么是JQuery

JQuery是JavaScript类库
封装了很多简单易用的方法
绝大多数用来简化dom操作

Jquery方法放在原型上

# JQuery事件绑定

~~~javascript
$('选择器').事件名(function(){
    //函数体
})
~~~



jquery取值时无法继续链式编程,设置值时可以链式编程

取值

```javascript
let $box1=$('.box1').html('<a href="#">黑马程序员</a>')
$box1.click(function(){console.log('1')})
//取值不可链式
```

# jquery常用AP

.frist() 匹配的第一个元素

.last()匹配的最后一个元素

.eq(索引)

## 样式操纵

```javascript
$('选择器').css('属性名','属性值')
$('.box').css({
bgc:'',
width:100
})
```

## 属性操纵

```javascript
.attr('属性名','值')
//赋值
.attr('属性名')
//取值
.removeAttr('属性名')
//删除属性
```

## 默认值获取赋值

```javascript
.val('fuzhi')
.val()取值
```

## 查找方法

```javascript
.parent（）
//父元素
.children（）
//子元素
.siblings（）
//兄弟元素
.find（'选择器'）
//后代元素
```

## 类名操纵

```javascript
.addClass('类名')
//添加类
.removeClass('类名')
//删除类
.hasClass('类名')
//是否包含类
.toggleClass('类名')
//切换类
```

## 事件进阶

```javascript
.click（）
//点击事件
.focus（）
//获得焦点事件
.input（）事件
.on（'事件名',回调函数）
//注册事件
.off（'事件名'）
//移除所有事件
.one（'事件名'，回调函数）
//注册一次性事件
```

## 触发事件

```javascript
.事件名（）
//直接触发
.trigger（'事件名'）
//trigger触发
.trigger（'自定义事件'）
//触发自定义事件
.on('自定义事件'，function（）{})
//注册自定义事件
```

## window事件绑定

```javascript
scroll（）滚动事件
```

## 获取元素位置

```javascript
$('选择器').offset()
//取值
$('选择器').position()
//取值
(top:  ,left:   )
//返回值

offset参照html标签
position参照离他最近有定位的祖先元素
offset会把外边距margin计算进去
position以外边距Margin为边界，不计算margin
```

## 获取元素滚动距离

```javascript
$('选择器').scrollLeft()
$('选择器').scrollTop()
//取值
$('选择器').scrollLeft(值)
$('选择器').scrollTop(值)
//赋值
```

# 动画

## 显示&隐藏动画

```javascript
$('选择器').show(持续时间)
//显示
$('选择器').hide(持续时间)
//隐藏
$('选择器').toggle(持续事件)
```

## 淡入淡出动画

```javascript
$('选择器').fadeIn()
//淡入
$('选择器').fadeOut()
//淡出
$('选择器').fadeToggle()
//淡入淡出
```

## 展开&收起动画

```javascript
$('选择器').slideDown()
//展开
$('选择器').sildeUp()
//收起
$('选择器').sildeToggle()
//展开收起
```

## 动画队列及停止方法

```javascript
$('选择器').stop()
//停止当前动画
$('选择器').stop(true)
//请空队列，在动画当前状态停止
$('选择器').stop(true,true)
//清空队列，知道当前动画的结束状态
```

## 自定义动画

```javascript
$('选择器').animate({动画属性})
```

# 插入节点

```javascript
$('父元素选择器').append(参数)
//父元素结尾
$('父元素选择器').prepend(参数)
//父元素开头
$('兄弟元素选择器').before(参数)
//兄弟元素前面
$('兄弟元素选择器').after(参数)
//兄弟元素后面
```

插入节点:传入创建的dom元素或者html结构
改变位置:传入现有的dom元素或者jQuery对象

# 动画回调函数

```javascript
$('选择器').基础动画方法(回调函数)
$('选择器').基础动画方法(持续时间，回调函数)
$('选择器').animate(属性，回调函数)
$('选择器').animate（属性，持续时间，回调函数）
```

## 动画的延迟方法

```javascript
$('选择器').delay(延迟时间).动画方法()
```

## 获取尺寸

```javascript
$('选择器').width()
//内容宽度
$('选择器').height()
//内容高度
$('选择器').innerWidth()
//内容+内边距宽度
$('选择器').innerHeight()
//内容+内边距高度
$('选择器').outerWidth()
//内容+内边距+边框宽度
$('选择器').outerHeight()
//内容+内边距+边框高度
$('选择器').outerWidth(true)
//内容+内边距+边框+外边距宽度
$('选择器').outerHeight(true)
//内容+内边距+边框+外边距高度
```

# 事件委托

## 事件参数

```javascript
stopPropagation（）
//阻止冒泡
preventDefault（）
//阻止默认行为
keycode=13为回车
```

## 删除节点

```javascript
jq对象.remove（）
删除元素节点
```

## 事件委托

```javascript
$('选择器').on('事件名'，function(){})
//直接绑定
$('祖先选择器').on('事件名'，'后代选择器',fucntion(){})
```

入口函数写法

```javascript
$(window).on('load',function(){})
$(document).ready(function(){})
//完整写法
$(function(){})
//简化写法
```

# 插件

## slick

轮播图

```javascript
必须插入css和jq

prevArrow 自定义 上一页 按钮

nextArrow 自定义 下一页 按钮

arrows 是否显示翻页按钮  true/false 默认true

autoplay 是否自动播放	true/false	默认false

dots 是否显示指示器(小圆点)	true / false 	默认 false
appendDots；“选择器”
```



## 懒加载

src改为data-original
$(‘类名’).lazyload

## 全屏滚动

fullpage

需要加载css和js插件和jquery插件

 navigation 是否显示导航条 默认false 

navigationPosition 导航位置 默认right     right/false

anchors 每个区域的锚链接名	默认值[‘类名‘，’‘，’‘] 备注（在地址栏） ，记录当前位置，快速回到当前位置

afterLoad 区域加载完毕的回调函数，返回有两个参数    参数：锚链接    索引

```
afterLoad(anchor，index){}
```

## 日期选择器

datepicker

导css jquery 日期选择器插件

| 常用配置 | 含义                 | 默认值 | 备注           |
| -------- | -------------------- | ------ | -------------- |
| autoPick | 是否自动选择当前日期 | false  | t/f            |
| autoHide | 选后是否自动关闭     | false  |                |
| language | 语言模式             | 空     | 结合语言包使用 |

## 表单验证插件

validate 

| 常用配置    | 含义                                 | 默认值 | 备注         |
| ----------- | ------------------------------------ | ------ | ------------ |
| onBlur      | 失去焦点时验证                       | false  |              |
| onSubmit    | 提交表单时验证                       | true   |              |
| sendFrom    | 是否提交表单                         | true   |              |
| valid       | 所有表单项验证通过执行的回调函数     | 无     | this是jq对象 |
| invalid     | 至少一个表单项为通过时执行的回调函数 | 无     | this是jq对象 |
| description | 错误提示信息                         | 无     | Object       |



| 自定义属性       | 含义                   | 备注                      |
| ---------------- | ---------------------- | ------------------------- |
| data-required    | 验证表单项不能为空     | 不需要值                  |
| data-pattern     | 基于正则表达式验证     | 正则表达式                |
| data-describedby | 指定显示错误信息的标签 | 标签的id                  |
| data-description | 指定错误信息的内容     | 和description中的属性对应 |

## 获取dom对象

使用中括号

使用get方法

```javascript
let $btn = $('button')
console.log('sbtn:' $btn)
// 1.get
let pauseBtn = $btn.get(1)
console.log('pauseBtn:', pauseBtn)
//2.中括号
let playBtn = $btn[0]
console.log('playBtn:' playBtn)
```

# 快速获取表单数据

叫做序列化

```javascript
$('form').seriazlize()
```

## 插件机制

```javascript
jQuery.fn.extend(){
	插件名(参数){
		//逻辑
	}
}
```

## 工具方法

```javascript
//遍历方法
$.each(数组，function（下标，值）{})

//遍历并返回新数组
$.map(数组，function（值）{
      返回新的值
      })
```

