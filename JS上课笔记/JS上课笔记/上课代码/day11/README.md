# 第十一天

## 数组的方法

- every()

  - 用来检查数组中的每一个元素是否都符合要求
    var result = arr.every((a)=>a>5);
  
- some()

  - 用来检查数组中是否有元素符合要求
    var result = arr.some((a)=>a>5);

- filter()

  - 用来从数组中筛选出符合条件的元素
    var result = arr.filter((a)=>a>5);
  

- map()

  - 根据原来的数组生成新的数组
    var result = arr.map((a)=>a+5);
    
- reduce()

  - 对数组中的元素进行汇总
    var result = arr.reduce((a,b)=>a+b);

- reverse()

  - 对数组中的元素进行反转，会影响到原来的数组

- sort()

  - 用来对数组进行排序，默认会按照元素的Unicode编码进行排序

  - 可以通过回调函数来指定排序规则：

    - 升序排列：
      arr.sort((a,b)=>a-b);

    - 降序排列
      arr.sort((a,b)=>b-a);

## 函数

- arguments

  - 在函数调用时，JS引擎会自动传递进两个隐含的参数this和arguments
  - arguments是一个类数组对象，调用函数时所用的实参都会存储在arguments对象中
  - 通过arguments可以在不定形参情况下，就访问实参
  - arguments[0]表示第一个实参，arguments[1]表示第二个实参 以此类推...
  - arguments.callee()用来表示当前调用的函数对象

- 剩余参数（rest）

  - 在定义形参时，可以使用如下方式定义剩余参数
      function fn(a, b, ...c) {
    }
  
  - 形参前跟着...则表示参数是剩余参数，剩余参数必须写在参数列表最后，所有的没有形参对应的实参都会保存到剩余参数的数组中。

- call()和apply()

  - 用来调用函数并指定函数的this
  - 不同点：
    - call()的参数需要一个一个的传递
    - apply()的参数需要通过数组（类数组）传递

- this的到底是谁？

  - 根据函数的调用方式不同，函数中的this也不同：
    - 以函数形式调用时，this是window
    - 以方法形式调用时，this是调用方法的对象
    - 以构造函数形式调用时，this是新建的对象
    - 使用call或apply调用时，this是call和apply的第一个参数
    - 全局作用域中的this是window
    - 箭头函数的this由外层作用域决定

- 解构赋值

  - 数组的解构
      var [a,b] = [3,4];
      var [c,d,...e] = [1,2,3,4,5,6];
    

  - 对象的解构
      var [name, age, ...other] = {name:'xxx',age:18,gender:'男',address:'xxxx'};
      ([name, age, ...other] = {name:'xxx',age:18,gender:'男',address:'xxxx'});
    

  - 实参的解构
      var arr = [1,2,3];
      fn(...arr);

- 递归

  - 函数自己调用自己的函数就是递归函数
  - 递归的核心思想是将一个大的问题，拆分为一个一个小的问题，然后各个击破
  - 递归的作用和循环是一样的，递归能处理的问题，通过循环也可以解决。循环的执行速度会比较快，递归会比较容易理解。
  - 在实际上开发中，递归也不会大量使用，尤其是对于刚进入公司工作的，尽量避免主动使用递归。
  - 递归的两个条件：
    - 基线条件，递归的停止条件！
    - 递归条件，如何对问题进行拆分！