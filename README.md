<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>动态弹幕示例</title>
<style>
  body {
    margin: 0;
    overflow: hidden;
    background: #111;
    color: white;
    font-family: Arial, sans-serif;
    position: relative;
    height: 100vh;
  }
  .danmu {
    position: absolute;
    white-space: nowrap;
    font-size: 20px;
    font-weight: bold;
  }
</style>
</head>
<body>

<script>
// 弹幕内容，可自由修改
const danmuList = [
  'Hello World!',
  '欢迎来到我的网站',
  '这是动态弹幕',
  'GitHub Pages 很方便',
  '我爱编程'
];

function createDanmu() {
  const text = danmuList[Math.floor(Math.random() * danmuList.length)];
  const danmu = document.createElement('div');
  danmu.className = 'danmu';
  danmu.textContent = text;
  danmu.style.top = Math.random() * (window.innerHeight - 30) + 'px';
  danmu.style.left = window.innerWidth + 'px';
  danmu.style.color = `hsl(${Math.random()*360}, 100%, 70%)`;
  document.body.appendChild(danmu);

  const speed = 2 + Math.random() * 3;
  const timer = setInterval(() => {
    const currentLeft = parseFloat(danmu.style.left);
    if (currentLeft + danmu.offsetWidth < 0) {
      danmu.remove();
      clearInterval(timer);
    } else {
      danmu.style.left = (currentLeft - speed) + 'px';
    }
  }, 16);
}

// 页面加载完成后开始生成弹幕
window.onload = function() {
  setInterval(createDanmu, 1000);
};
</script>

</body>
</html>
