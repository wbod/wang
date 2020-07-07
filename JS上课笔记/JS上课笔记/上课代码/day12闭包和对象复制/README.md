## 第十二天

## 排序算法

- 冒泡排序（bubble）

  - 原理：反复的比较相邻的两个元素的大小，然后根据需要进行交换位置

  - 性能比较差，不适用元素较多的情况
    var arr = [3,4,1,2,6,7,9,0,5,8];
    
    // 排列次数的最大应该为数组的长度-1
    for(var j=0; j<arr.length-1; j++){
        //获取到数组中的每一个元素
        for(var i=0; i<arr.length-1; i++){
        //比较当前元素和后一个元素的大小
        //当前元素 arr[i]  后一个元素arr[i+1]
            if(arr[i] > arr[i+1]){
                // 前边的元素大于后边的元素，交换两个元素的位置
                var temp = arr[i];
                arr[i] = arr[i+1];
                arr[i+1] = temp;
            }
        }
    }
  

- 快速排序（quick）
  - 原理：从数组中提取出一个基准值，比基准值大的放到其右侧，比它小的放到其左侧
  - 性能好
    var arr = [3,4,1,2,6,7,9,0,5,8]; 
    //创建一个快速排序的函数
    // 对array进行排序，返回一个排好序的新数组
    function quickSort(array) {
        //设置基线条件
        if(array.length <= 1){
        return array;
        }
        // 获取一个基准值，获取数组的最后一个元素作为基准值
        var base = array[array.length-1];
    
        //创建两个数组
        var left = []; //左数组，存储小于base的元素
        var right = []; //右数组，存储大于base的元素
    
        //比较每个元素和base的大小
        for(var i=0; i<array.length - 1; i++){
            // 比较当前值和基准值的大小
            if(array[i] < base){
                //放入到左数组
                left.push(array[i]);
            }else{
                //放入到右数组
                right.push(array[i]);
        	}
    	}
    
        //left base right
        // 将left base right 拼接为一个数组返回
        return quickSort(left).concat(base, quickSort(right));
    }
    
    var result = quickSort(arr);
    ```

## 闭包

- 闭包就是可以访问到外部函数中变量的内部函数

- 闭包的创建：

  1. 必须有函数的嵌套
  2. 内层函数必须要引用外层函数中的变量
  3. 将内层函数作为返回值返回

- 例子：

  - ```javascript
    function outer(){
    	var a = 10;
    	function inner(){
    		console.log(a);
    	}
    	return inner;
    }
    var fn = outer();
    ```

- 特点：

  - 闭包在外部函数调用时创建
  - 外部函数每调用一次就产生一个闭包
  - 当内部函数都被垃圾回收闭包即被销毁
  - 应用闭包主要是为了隐藏一些不希望被外部访问的变量

## 对象的复制（拷贝）

- 浅复制
  - 浅复制表示只复制对象的自身，不复制对象的属性
  - 性能比较好
  - 数组的浅复制：
    - slice()
  - 对象的浅复制
    - assign()
- 深复制
  - 深复制不仅会复制对象的自身，同时也会复制对象的属性，甚至是属性的属性
  - 性能差

## 日期对象（Date）

- 在JS中，所有和时间相关信息都由Date对象来表示

- 创建日期对象：

  - 创建一个当前日期对象

    var d = new Date();

  - 创建一个指定的日期对象

    var d = new Date('月份/日/年份 时:分:秒');
  
  

- 对象方法：

  - getFullYear()
    - 获取当前日期对象的年份
  - getMonth()
    - 获取当前日期对象的月份
    - 从0开始，0表示1月，1表示2月...
  - getDate()
    - 获取当前日期对象是几日
  - getDay()
    - 获取当前日期对象是周几
    - 从0开始，0表示周日，1表示周一...
  - getTime()
    - 获取当前日期对象的时间戳
    - 时间戳指从1970年1月1日0时0分0秒到现在时刻所经历的毫秒数
    - 在计算机底层所有的时间都是通过时间戳表示的
    - 时间戳会1ms生成一个，重复的几率极低，所以时间戳经常用来生成一些随机的id
  - Date.now()
    - 类方法（静态方法），直接通过函数对象来调用
    - 用来直接获取到当前时间的时间戳

