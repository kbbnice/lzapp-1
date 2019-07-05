##### less

1. 清除浮动： 

   ```less
   .clearfix {
       display: block;
       zoom: 1;
       &:after {
           content: " ";
           display: block;
           font-size: 0;
           heigtht: 0;
           clear： both;
           vasibility: hidden;
       }
   }
   ```

   

2. referencing parent selectors: 引用父类选择器：`&`

   ```less
   a {
       color: blue;
       &:hover {
           color: green;
       }
   }
   ```

   

   a. 父类选择器`&` 可以拼接使用：

   ```less
   .button {
       &-ok {
           color: red;
       }
       &-cancel {
           color: green;
       }
   }
   
   
   /* 以上渲染出来结果为： */
   .button-ok {
       color: red;
   }
   .button-cancel {
       color: green;
   }
   ```

   

3. **注意：引用父类选择器`&` 选择的是所有的父类选择器**

   ```less
   /* 例如 */
   .grand {
       .parent {
           & > & {
               color: red;
           }
           & & {
               color: green;
           }
           && {/* .grand .parent.grand .parent */
               color: pink;
           }
           &, &ish {
               color: blue;
           }
       }
   }
   
   /* 以上代码等同于 */
   
   .grand .parent > .grand .parent {
       color: red;
   }
   .grand .parent .grand .parent {
       color: green;
   }
   .grand .parent.grand .parent {
       color: pink;
   }
   .grand .parent,
   .grand .parentish {
       color: blue;
   }
      
   ```

   

4. 改变选择器顺序: .

   ```less
   .header {
       .menu {
           border: 1px solid pink;
           .no-border & {
               color: red;
           }
       }
   }
   
   /* 以上代码相当于 */
   .header .menu {
       border: 1px solid red;
   }
   .no-border .header .menu {
       color: red;
   }
   ```

   

5. 创建所有可能组合:

   ```less
   p, a, ul, li {
       border-top: 1px solid red;
       & + & { /* 加号是选择紧挨在该选择器后的同父元素下的兄弟元素 */
           border-top: 0;
       }
   }
   
   /* 相当于 */
   
   p, a ul li {
       border-top: 1px solid red;
   }
   p + p,
   p + a,
   p + ul,
   p + li,
   a + p,
   a + a,
   a + ul,
   a + li,
   ul + p,
   ul + a,
   ul + ul,
   ul + li,
   li + p,
   li + a,
   li + ul,
   li + li {
     border-top: 0;
   }
   
   ```

   

6. 

   

   ```css
   stylus  ---是另一种预编译css的东西
   ```

   