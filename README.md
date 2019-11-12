# Canvas 教程

### 开始绘制

```HTML
布置画布：通过添加<canvas>标签，添加canvas元素

获取画布：通过<canvas>标签的id，获得canvas对象

获得画笔：通过canvas对象的getContext("2d")方法，获得2D环境
```

```JavaScript
// DOM 结构
<canvas id=“canvas”></canvas>

// JS 获取元素
var canvas = document.getElementById("canvas");

// 取得 Canvas 2D 环境
var context = canvas.getContext("2d");
```

### 绘制线段

移动画笔: `moveTo(x, y)`

笔画停点: `lineTo(x ,y)`

画笔粗心: `lineWidth(number)`

画笔颜色: `strokeStyle = HEX`

填充颜色: `fillStyle = 'HEX'`

绘制方式: `fill()` 填充, `stroke()` 描边


> 需要注意的是，为了让绘制方法不重复绘制，我们需要在每次绘制之前加上 `beginPath()` , 在绘制之后加上 `closePath()` 闭合画笔 。


### 使用 rect() 函数绘制矩形

我们先来绘制一个矩形

```JavaScript
  // 开始绘制
  var canvas = document.getElementById("canvas");
  canvas.width = 800;
  canvas.height = 600;
  var context = canvas.getContext("2d");
  // 路径绘制
  context.moveTo(100,100); // 移动画笔
  context.lineTo(200,100); // 画笔落点
  context.lineTo(200,200); // 画笔落点
  context.lineTo(200,200); // 画笔落点
  context.lineTo(100,200); // 画笔落点
  context.lineTo(100,100); // 画笔落点
  context.closePath(); // 闭合图形
  context.lineWidth = 5; // 画笔粗细
  context.fillStyle = '#ff0'; // 填充颜色
  context.strokeStyle = "#AA394C"; //画笔颜色
  context.fill(); // 开始绘制
```

**如果我们要绘制多个矩形，我们就需要用到 `rect(x, y, width, height)`**

```JavaScript
  // 开始绘制
  var canvas = document.getElementById("canvas");
  canvas.width = 800;
  canvas.height = 600;
  var context = canvas.getContext("2d");
  // 路径绘制
  drawRect(context, 150, 50, 50, 50, "red", 5, "blue");

  // 封装方法
  function drawRect (cxt, x, y, width, height, fillColor, borderWidth, borderColor) {
    cxt.beginPath();
    // 使用 rect 方法
    cxt.rect(x, y, width, height);
    // 画笔样式
    cxt.lineWidth = borderWidth;
    cxt.strokeStyle = borderColor;
    cxt.fillStyle = fillColor;
    // 绘制方式
    cxt.fill();
    cxt.stroke();
  }
```
 