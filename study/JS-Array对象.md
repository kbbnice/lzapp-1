`concat()`方法

1. 用于连接两个或多个数值。

   ```javascript
   arrayObj.concat(arrX, arr2, arr4);
   ```

2. `arrX`参数：必须。

   > 1. 可以是具体的的值；
   > 2. 可以是数组对象；
   > 3. 可以是任意多个。

3. 返回值：

   ```
   > 将所有arr参数添加到arrayObject中生成。
   > 如果concat方法操作的参数是数组arrX中的元素，而不是整个数组。
   > 返回一个新的数组。
   ```

4.  实例：

   ```javascript
   var arr  = [1, 2, 4];
   var arr2 = [3, 6, 7];
   
   var newArr = arr.concat(arr2);
   console.log(newArr);
   
   //返回： [1, 2, 4, 3, 6, 7]; arr和arr2的值不变。
   
   ```

   