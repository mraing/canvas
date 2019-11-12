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

画笔颜色: `strokeStyle(HEX)`

绘制方式: `fill()` 填充, `stroke()` 描边


> 需要注意的是，为了让绘制方法不重复绘制，我们需要在每次绘制之前加上 `beginPath()` , 在绘制之后加上 `closePath()` 。

