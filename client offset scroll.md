### clientWidth、offsetWidth、scrollWidth等的区别
---
#### 一、 clientWidth和clientHeight、clientTop和clientLeft
1. clientWidth的实际宽度
- clientWidth = width + 左右padding
2. clientHeight的实际高度
- clientHeight = height + 上下padding
3. clientTop的实际宽度
- clientTop = border-top-width (上边框的宽度)
4. clientLeft的实际宽度
- clientLeft = border-left-width (左边框的宽度)

##### 总的来说clientWidth和clientHeight指的就是padding box的宽度和高度

---
#### 二、 offsetWidth和offsetHeight、offsetTop和offsetLeft
1. offsetWidth的实际宽度
- offsetWidth = width + 左右padding + 左右border
2. offsetHeight的实际高度
- offsetHeight = height + 上下padding + 上下border
3. offsetTop的实际宽度
- offsetTop = 当前元素的上边框外边缘到最近的定位父级元素 (offserParent) 的上边框的内边缘的距离
4. offsetLeft的实际宽度
- offsetLeft = 当前元素的左边框外边缘到最近的定位父级元素 (offserParent) 的左边框的内边缘的距离

##### 总的来说offsetWidth和offsetHeight指的就是border box的宽度和高度

---
#### 三、 scrollWidth和scrollHeight、scrollTop和scrollLeft
1. scrollWidth的实际宽度
- scrollWidth = 当前元素内容的实际宽度 (可视内容区的宽度 + 被隐藏的内容的宽度)
2. scrollHeight的实际高度
- scrollHeight = 当前元素内容的实际高度 (可视内容区的高度 + 被隐藏的内容的高度)
3. scrollTop的实际宽度
- scrollTop = 当前元素内容的顶部到上padding的上边缘的距离
4. scrollLeft的实际宽度
- scrollLeft = 当前元素内容的左侧到左padding的左边缘的距离

---
####具体细节请查看下图：

![avatar](https://upload-images.jianshu.io/upload_images/3555389-22caf4ed928d9b7f.jpg)