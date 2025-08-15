灌灌灌灌会更好
法国公关部
方法反反复复反反复复


反反复复反反复复凤飞飞








反反复复反反复复凤飞飞发发发


反反复复凤飞飞反反复复方法








滴答滴答滴答滴答滴答滴答哒哒哒哒哒哒大V






的点点滴滴的点点滴滴哒哒哒哒哒哒
的点点滴滴的点点滴滴哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒










对对对对对对的点点滴滴哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒哒但是事实上事实上事实上是撒是撒是撒是撒是撒是撒是撒是撒是撒是撒是撒
额滴答滴答滴答滴答滴滴答答哒哒哒哒哒哒哒哒哒哒哒哒






吧gggggggggggggggggggggggggggggggggggggggggggggggggggggggggggggggg






反反复复反反复复凤飞飞发发发发发发发发发发发发发发发发发发发发发发发发发发发发

<img width="780" height="342" alt="image" src="https://github.com/user-attachments/assets/51713d03-2600-4604-af8a-4684ccef932f" />




很尴尬个孤寡孤寡孤寡嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎嘎


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
    font-size: 16px; /* 字号稍微小一点 */
    font-weight: bold;
    white-space: nowrap;
    box-sizing: border-box;
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
  '明星‘再就业’？内娱我看不懂了！',
  '每天播够六小时才算达标，这工时比流水线还狠吧',
  '签约三年不能解约，违约金高得能压垮普通家庭',
  '表面光鲜亮丽，其实连社保都没人给缴',
  '团播合同全是坑，谁敢去？！',
  '其实都是资本的圈钱工具',
  '团播就是吃青春饭罢了',
  '每天练舞到凌晨，月薪还没服务员高',
  '团播到期就失业，没学历没技能，转行都难',
  '为了数据好看，被逼着和粉丝搞暧昧，违背本心',
  '全年无休连轴转，生病都得硬撑着播，这哪是工作是卖命',
  '公司拿着你的直播收益投资新人，你火了就被榨干价值',
  '说是团队合作，其实暗地里抢资源抢镜头，勾心斗角没停过',
  '年纪轻轻就被圈在直播间，社交圈窄得可怜，朋友都没几个'
];

function createDanmu(text) {
  const danmu = document.createElement('div');
  danmu.className = 'danmu';
  danmu.textContent = text;

  const centerX = window.innerWidth / 2 - 100; // 向左偏移100px
  const centerY = window.innerHeight / 2;

  danmu.style.left = (centerX + (Math.random()-0.5)*400) + 'px';
  danmu.style.top = (centerY + (Math.random()-0.5)*400) + 'px';

  const angle = (Math.random() - 0.5) * 45;
  danmu.style.transform = `rotate(${angle}deg)`;

  if(Math.random() < 0.5) {
    // 白色弹幕: 白底黑字 + 细黑色外描边
    danmu.style.color = '#000000';
    danmu.style.border = '2px solid #FFFFFF';
    danmu.style.background = '#FFFFFF';
    danmu.style.boxShadow = '0 0 0 1px #000000';
  } else {
    // 紫色弹幕: 紫底黑字 + 细白色外描边
    danmu.style.color = '#000000';
    danmu.style.border = '2px solid #9D4EDD';
    danmu.style.background = '#9D4EDD';
    danmu.style.boxShadow = '0 0 0 1px #FFFFFF';
  }

  document.body.appendChild(danmu);
}

let hasTriggered = false;
const triggerArea = document.getElementById('trigger-area');

function triggerDanmu() {
  if (!hasTriggered) {
    hasTriggered = true;
    danmuList.forEach((text, i) => {
      // 后面的弹幕速度稍微快一点
      setTimeout(() => createDanmu(text), i * 400);
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
