# 第十六天

## this到底是谁？

- 根据函数的调用方式不同this的值也不同
  1. 以函数形式调用时，this是window
  2. 以方法形式调用时，this是调用方法的对象
  3. 以构造函数形式调用时，this是新建的对象
  4. 使用call和apply调用时，this是call和apply的第一个参数
  5. 箭头函数中的this，由外层作用域决定
  6. 事件响应函数中的this，是绑定事件的对象

## DOM的增删改

- 根据标签名创建一个元素节点

  - ```javascript
    document.createElement('标签名')
    ```

- 根据文本内容创建一个文本节点（不太常用）

  - ```javascript
    document.createTextNode('文本内容');
    ```

- 向父节点中添加子节点

  - ```javascript
    父节点.appendChild(子节点);
    ```

- 将节点添加到某个节点的前边

  - ```javascript
    父节点.insertBefore(前边, 后边);
    ```

- 使用节点替换已有节点

  - ```javascript
    父节点.replaceChild(新的, 旧的);
    ```

- 删除节点

  - ```javascript
    父节点.removeChild(子节点);
    子节点.parentNode.removeChild(子节点);
    ```

- 也可以通过innerHTML来完成DOM的增删改