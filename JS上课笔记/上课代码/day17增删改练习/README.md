# 第十七天

## 样式的操作

- 样式指直接通过JS来操作页面中的CSS样式

- 内联样式：

    元素.style.属性名

    元素.style.属性名 = 属性值
  

- 读取计算的样式

  - getComputedStyle()
    - 用来获取元素当前的样式
    - 参数：
      1. 要读取样式的对象
      2. 要读取伪元素
    - 返回值：
      - 返回一个对象，对象中存储了当前元素的所有样式

- 注意：

  - 通过JS读取样式时，如果样式名中带有-，必须对样式名进行修改，将-去掉，-后的字母改大写
    - 例如：background-color  写为  backgroundColor
  - 通过JS读取到的样式都是带有单位，通常不能直接计算
  - getComputedStyle()不支持IE8及以下的浏览器，在IE8以下的浏览器中需要使用currentStyle来获取元素当前的样式

- 其他的样式相关的属性

  - offsetWidth
  - offsetHeight
    - 获取元素的可见框的大小（内容区、内边距和边框）
    
  - offsetParent
    - 获取元素的定位父元素
    - 距离元素最近的开启了定位的祖先元素，如果所有的祖先元素都没有开启定位则返回body

  - offsetLeft
  - offsetTop
    - 获取元素距离定位父元素的水平和垂直偏移量

  - clientWidth
  - clientHeight
    - 获取元素可见区域的大小（内容区、内边距）

  - scrollWidth
  - scrollHeight
    - 获取元素的滚动区域的大小

  - scrollTop
  - scrollLeft
    - 获取或设置元素垂直和水平滚动条的位置

  - 检查垂直滚动条滚动到底
    - Math.round(scrollHeight - scrollTop) === clientHeight

  - 检查水平滚动条滚动到底
    - Math.round(scrollWidth - scrollLeft) === clientWidth