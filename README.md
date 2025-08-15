 <header>欢迎来到我的网站</header>
  <main>
    <h2>Hello World！</h2>
    <p>这是我用 GitHub Pages 搭建的第一个网页 🎉</p>
    <p>你也可以在这里添加图片、链接、弹幕等内容。</p>
  </main>
</body>
</html>
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>动态弹幕示例</title>
<style>
  body {
    margin: 0;
    overflow: hidden;
    background: #111;
    color: white;
    font-family: Arial, sans-serif;
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
  danmu.style.top = Math.random() * window.innerHeight + 'px';
  danmu.style.left = window.innerWidth + 'px';
  danmu.style.color = `hsl(${Math.random()*360}, 100%, 70%)`; // 随机颜色
  document.body.appendChild(danmu);

  const speed = 2 + Math.random() * 3; // 弹幕速度
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

// 每 1 秒生成一条弹幕
setInterval(createDanmu, 1000);
</script>

</body>
</html>
