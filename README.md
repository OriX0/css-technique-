## css-technique

### 关于本仓库

1. 记录觉得有趣的css知识 
2. 记录工作中常用的布局套路
3. 总结对应问题的调试方法

### 移动端布局

1. 移动端交互中的不同

   1. 没有hover事件
   2. 有touch事件
   3. 没有resize
   4. 没有滚动条  （移动端看到的滚动条都是定位器 而非滚动条）

2. 使用media query  

3. 隐藏元素实现多端的变化

4. 手机端需要加一个 meta `<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no"/>`

5. 对于设计稿的像素与实际像素

   1. css像素 =设计稿中的像素值/像素比

   2. 设置meta中的标签为  1/像素比

      ```js
      var scale = 1 / window.devicePixelRatio;
      // 计算像素比
      
      document.querySelector('meta[name="viewport"]').setAttribute('content','width=device-width,initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');
      // 生成meta头
      ```

      

### 堆叠顺序

#### 调试技巧

- 使用 margin 调整位置(不会影响堆叠顺序)
- 调试文字的时候 使用 输入法的 特殊符号里面 填充的表情  能明确的看到覆盖 推荐 `■`

#### 自底--->顶   

1. z-index为负的元素
2. background
3. border
4. div/块级元素
5. 浮动元素
6. 文字/内联（包括 inline-block）
7. 绝对定位的元素（默认z-index 为0  或者 auto）
8. z-index为正整数的元素

