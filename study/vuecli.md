##### vue.config.js

###### 修改标题favicon.ico

1. ```
   // 在vue.config.js中添加 pwa 属性：
   
   module.exports = {
     pwa: {
       iconPaths: {
         favicon32: 'favicon.ico',
         favicon16: 'favicon.ico',
         appleTouchIcon: 'favicon.ico',
         maskIcon: 'favicon.ico',
         msTileImage: 'favicon.ico'
       }
     }
   ```

2. 