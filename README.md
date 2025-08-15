<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>固定弹幕示例</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@400;700&display=swap');
  body {
    margin: 0;
    overflow: hidden;
    background: #111;
    font-family: 'Roboto Slab', serif;
    height: 200vh;
    position: relative;
  }
  #trigger-area {
    height: 100vh;
    position: relative;
  }
  .danmu {
    position: absolute;
    padding: 5px 10px;
    border-radius: 5px;
    background: #FFFFFF;
    font-size: 18px;
    font-weight: bold;
    white-space: nowrap;
  }
</style>
</head>
<body>

<div id="trigger-area"></div>

<script>
const danmuList = [
  '全程假笑不累吗？一个个跟提线木偶似的，一点真实感没有',
  '下班看跳舞解压，花钱买快乐，值了',
  '跳仨小时没见 C 位？没刷火箭不配露脸呗',
  '就这水平还好意思开付费打赏？割韭菜也得讲点良心吧',
  '其实很多团播的小姐姐真的还挺好看的！',
  '机构抽四成平台抽五成，主播喝西北风啊？',
  '扭胯泼水老三样，擦边擦出火星子👋',
  '就喜欢看！我乐意花钱，咋滴，你打我啊',
  '这团人也太多了吧？镜头扫一圈根本记不住谁是谁',
  '美颜开成外星人，亲妈都不认得',
  '年轻人困在直播间，青春全喂狗了',
  '为什么搞团播，不都是为了钱',
  '又是这套流程？能不能换点新花样啊，看腻了',
  '弹幕全是‘守护 XX’，怕都是水军吧？',
  '就一支舞跳来跳去，无聊得抠别墅…',
  '说好月入三万到手五千，纯纯诈骗！',
  '其实团播真没你们想的那么乱...',
  'PK 输了罚深蹲？直播间搞职场 PUA 呢！',
  '全员蛇精脸大长腿，量产爱豆没特点',
  '下播还得私聊大哥‘写作业’，这班狗都不上🙄',
  '无聊，低俗！到底是谁在看团播',
  '脱下孔乙己长衫，穿上擦边戏服😅',
  '就这水平？我感觉我上也能行',
  '明星‘再就业’？内娱我看不懂了！'
];

function createDanmu(text) {
  const danmu = document.createElement('div');
  danmu.className = 'danmu';
  danmu.textContent = text;

  const centerX = window.innerWidth / 2;
  const centerY = window.innerHeight / 2;

  danmu.style.left = (centerX + (Math.random()-0.5)*400) + 'px';
  danmu.style.top = (centerY + (Math.random()-0.5)*400) + 'px';

  const angle = (Math.random() - 0.5) * 45;
  danmu.style.transform = `rotate(${angle}deg)`;

  danmu.style.color = Math.random() < 0.5 ? '#000000' : '#9D4EDD';

  document.body.appendChild(danmu);
}

let hasTriggered = false;
const triggerArea = document.getElementById('trigger-area');

function triggerDanmu() {
  if (!hasTriggered) {
    hasTriggered = true;
    danmuList.forEach((text, i) => {
      setTimeout(() => createDanmu(text), i * 600); // 给阅读时间
    });
  }
}

window.addEventListener('DOMContentLoaded', triggerDanmu);
window.addEventListener('scroll', () => {
  const rect = triggerArea.getBoundingClientRect();
  if (rect.top < window.innerHeight && rect.bottom > 0) {
    triggerDanmu();
  }
});
</script>

</body>
</html>
