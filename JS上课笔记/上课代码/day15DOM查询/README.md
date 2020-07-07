# 第十五天

## 网页的加载

- 网页的加载顺序是自上向下一行一行加载，一行一行执行

- 如果将JS代码写在页面的最上方，那么它会优先于HTML代码执行，这样将会导致无法正常获取到DOM对象

- 解决方案：

  - 方案一：将JS代码直接编写在body标签的最后
      <body>
      
          <script>
              // JS代码
          </script>
      </body>

  - 方案二：将JS代码编写在window.onload的回调函数中
      window.onload = function(){
      	// JS代码
      };

## DOM查询

- Document对象的方法

  - 根据元素id属性获取一个元素

      document.getElementById()

  - 根据元素的class属性获取一组元素

      document.getElementsByClassName()

  - 根据元素的标签名获取一组元素

      document.getElementsByTagName()

  - 获取页面中的所有元素

      document.getElementsByTagName('*')

  - 根据选择器字符串获取一个元素
      document.querySelector()

  - 根据选择器字符串获取一组元素

      document.querySelectorAll()

  - 根据元素的name属性获取一组元素

      document.getElementsByName()

  - 获取网页的body元素

      document.body

  - 获取网页中的根元素

      document.documentElement

- Element元素对象的属性和方法

  - 根据标签名获取指定元素的后代元素

      ele.getElementsByTagName

  - 获取当前元素的所有子节点

      ele.childNodes

  - 获取当前元素的所有子元素

      ele.children


  - 获取当前元素第一个子节点

      ele.firstChild
    
  - 获取当前元素的最后一个子节点

      ele.lastChild
      

  - 获取当前元素的第一个/最后一个子元素

      ele.firstElementChild
      ele.lastElementChild
     

  - 获取当前元素的父节点

      ele.parentNode
    

  - 获取当前元素前一个/后一个兄弟节点

      ele.previousSibling
      ele.nextSibling
      

  - 获取当前元素的前一个/后一个兄弟元素

      ele.previousElementSibling
      ele.nextElementSibling
    

- 读取对象的属性

  - 语法：对象.属性

    - 例子：

        ele.value
        ele.id
        ele.name
        ele.className
    

- 设置对象的属性

  - 语法：对象.属性 = 值

    - 例子：

        ele.value = 'xx'
        ele.id = 'yy'
        ele.name = 'zz'
        ele.className = 'hh'
      

- 读取标签内部的html代码
  - ele.innerHTML 直接返回内部的html代码（带标签）
  - ele.innerText 直接返回内部的文本内容（去标签）
    - 在通过innerText设置文本内容时，它会自动对标签内容进行转义，也就是标签会直接在页面中显示
    - 它会自动的最特殊符号进行转义，以使特殊符号直接显示