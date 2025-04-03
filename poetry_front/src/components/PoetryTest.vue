<template>
  <div class="all">
    <div id="mtapp">
      <div class="containerww">

<img src="../assets/image/imgtest/WechatIMG1856.png" alt="Image" class="top-right-image2">
<img src="../assets/image/imgtest/WechatIMG1857.png" alt="Image" class="top-right-image3">
<img src="../assets/image/imgtest/WechatIMG1921.png" alt="Image" class="top-right-image35">
<img src="../assets/image/imgtest/WechatIMG1858.png" alt="Image" class="top-right-image4">
<img src="../assets/image/imgtest/WechatIMG1859.png" alt="Image" class="top-right-image5">
<img src="../assets/image/imgtest/WechatIMG1861.png" alt="Image" class="top-right-image6">
<img src="../assets/image/imgtest/WechatIMG1862.png" alt="Image" class="top-right-image7">
<img src="../assets/image/imgtest/WechatIMG1863.png" alt="Image" class="top-right-image8">
<img src="../assets/image/imgtest/WechatIMG1871.png" alt="Image" class="top-right-image9">
<img src="../assets/image/imgtest/WechatIMG1872.png" alt="Image" class="top-right-image10">
<img src="../assets/image/imgtest/WechatIMG1873.png" alt="Image" class="top-right-image11">
<img src="../assets/image/imgtest/WechatIMG1874.png" alt="Image" class="top-right-image12">
<img src="../assets/image/imgtest/WechatIMG1875.png" alt="Image" class="top-right-image13">


<img src="../assets/image/imgtest/WechatIMG1876.png" alt="Image" class="top-left-image2">
<img src="../assets/image/imgtest/WechatIMG1877.png" alt="Image" class="top-left-image3">
<img src="../assets/image/imgtest/WechatIMG1732.png" alt="Image" class="top-left-image4">
<img src="../assets/image/imgtest/WechatIMG1876.png" alt="Image" class="top-left-image5">
<img src="../assets/image/imgtest/WechatIMG1877.png" alt="Image" class="top-left-image6">
<img src="../assets/image/imgtest/WechatIMG1878.png" alt="Image" class="top-left-image7">
<img src="../assets/image/imgtest/WechatIMG1879.png" alt="Image" class="top-left-image8">
<img src="../assets/image/imgtest/WechatIMG1882.png" alt="Image" class="top-left-image9">
<img src="../assets/image/imgtest/WechatIMG1883.png" alt="Image" class="top-left-image10">
<img src="../assets/image/imgtest/WechatIMG1951.png" alt="Image" class="top-left-image11">
<img src="../assets/image/imgtest/WechatIMG1885.png" alt="Image" class="top-left-image12">
<img src="../assets/image/imgtest/WechatIMG1886.png" alt="Image" class="top-left-image13">



</div>
      <div class="container">
        <div class="bubble" v-for="i in 18" :key="i" :style="{ '--i': i }"></div>
      
      <div class="bg">
    <br><br>
    <h1>奥运知识问答</h1>
    <div class="progress-container">
      <svg class="progress-circle" viewBox="0 0 36 36">
        <path class="circle-bg" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
        <path class="circle" :stroke-dasharray="progressPercentage + ', 100'" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
      </svg>
<div class="progress-text" @click=" handleProgressClick()">
  {{
    showResultsFlag // 如果已经显示答案
      ? "再来一遍"  // 显示"再来一遍"
      : (answeredQuestionsCount === 15 ? "查看结果" : answeredQuestionsCount + "/15") 
  }}
</div>

<!-- 弹窗 -->
<div v-if="isModalVisible" class="modal-overlay">
  <div class="modal">

    <img src="../assets/image/imgtest/WechatIMG1951.png" alt="Image" class="left-image">
    <h2 v-if="correctCount <= 7">奥运知识新星</h2>
    <h2 v-else-if="correctCount <= 12">奥运知识先锋</h2>
    <h2 v-else>奥运知识达人</h2>
    <p>你答对了 {{ correctCount }} 道题！</p>
    <button @click="confirm()">返回查看答案</button>

    <img src="../assets/image/imgtest/WechatIMG1874.png" alt="Image" class="right-image">
  </div>

</div>
    </div>

    <div class="test">
     <!-- Question 1 -->
<div class="a">
  <p>1. 本届奥运中国首金获得者盛李豪的id是？</p>
  <div>
    <button :class="buttonState('a1')" @click="changeScore('a1', 'a2', 'a3', 'a4')" :disabled="showResultsFlag">A.只靠干饭就</button>
    <button :class="buttonState('a2')" @click="changeScore('a2', 'a1', 'a3', 'a4')" :disabled="showResultsFlag">B.光靠干饭就</button>
  </div>
  <div>
    <button :class="buttonState('a3')" @click="changeScore('a3', 'a1', 'a2', 'a4')" :disabled="showResultsFlag">C.靠干饭就</button>
    <button :class="buttonState('a4')" @click="changeScore('a4', 'a1', 'a2', 'a3')" :disabled="showResultsFlag">D.只靠吃饭就</button>
  </div>
</div>

<!-- Question 2 -->
<div class="a">
  <p>2. 本届奥运开幕式致敬了哪部法国新浪潮电影？</p>
  <div>
    <button :class="buttonState('z1')" @click="changeScore('z1', 'z2', 'z3', 'z4')" :disabled="showResultsFlag">A.《祖与占》</button>
    <button :class="buttonState('z2')" @click="changeScore('z2', 'z1', 'z3', 'z4')" :disabled="showResultsFlag">B.《筋疲力尽》</button>
  </div>
  <div>
    <button :class="buttonState('z3')" @click="changeScore('z3', 'z1', 'z2', 'z4')" :disabled="showResultsFlag">C.《登堂入室》</button>
    <button :class="buttonState('z4')" @click="changeScore('z4', 'z1', 'z2', 'z3')" :disabled="showResultsFlag">D.《乱世佳人》</button>
  </div>
</div>

<!-- Question 3 -->
<div class="a">
  <p>3. “这能说吗？”的采访梗出自哪位中国运动员？</p>
  <div>
    <button :class="buttonState('b1')" @click="changeScore('b1', 'b2', 'b3', 'b4')" :disabled="showResultsFlag">A.郑钦文</button>
    <button :class="buttonState('b2')" @click="changeScore('b2', 'b1', 'b3', 'b4')" :disabled="showResultsFlag">B.潘展乐</button>
  </div>
  <div>
    <button :class="buttonState('b3')" @click="changeScore('b3', 'b1', 'b2', 'b4')" :disabled="showResultsFlag">C.全红婵</button>
    <button :class="buttonState('b4')" @click="changeScore('b4', 'b1', 'b2', 'b3')" :disabled="showResultsFlag">D.王楚钦</button>
  </div>
</div>

<!-- Question 4 -->
<div class="a">
  <p>4. 中国队在本届奥运哪一项目包揽了全部金牌？</p>
  <div>
    <button :class="buttonState('c1')" @click="changeScore('c1', 'c2', 'c3', 'c4')" :disabled="showResultsFlag">A.篮球</button>
    <button :class="buttonState('c2')" @click="changeScore('c2', 'c1', 'c3', 'c4')" :disabled="showResultsFlag">B.乒乓球</button>
  </div>
  <div>
    <button :class="buttonState('c3')" @click="changeScore('c3', 'c1', 'c2', 'c4')" :disabled="showResultsFlag">C.艺术体操</button>
    <button :class="buttonState('c4')" @click="changeScore('c4', 'c1', 'c2', 'c3')" :disabled="showResultsFlag">D.举重</button>
  </div>
</div>

<!-- Question 5 -->
<div class="a">
  <p>5. 获得巴黎奥运会奖牌最多的运动员是？</p>
  <div>
    <button :class="buttonState('d1')" @click="changeScore('d1', 'd2', 'd3', 'd4')" :disabled="showResultsFlag">A.张雨霏</button>
    <button :class="buttonState('d2')" @click="changeScore('d2', 'd1', 'd3', 'd4')" :disabled="showResultsFlag">B.潘展乐</button>
  </div>
  <div>
    <button :class="buttonState('d3')" @click="changeScore('d3', 'd1', 'd2', 'd4')" :disabled="showResultsFlag">C.拜尔斯</button>
    <button :class="buttonState('d4')" @click="changeScore('d4', 'd1', 'd2', 'd3')" :disabled="showResultsFlag">D.费尔南德斯</button>
  </div>
</div>

<!-- Question 6 -->
<div class="a">
  <p>6. 郑钦文选手在半决赛击败了哪位选手成功进军决赛？</p>
  <div>
    <button :class="buttonState('e1')" @click="changeScore('e1', 'e2', 'e3', 'e4')" :disabled="showResultsFlag">A.斯瓦泰克</button>
    <button :class="buttonState('e2')" @click="changeScore('e2', 'e1', 'e3', 'e4')" :disabled="showResultsFlag">B.科贝尔</button>
  </div>
  <div>
    <button :class="buttonState('e3')" @click="changeScore('e3', 'e1', 'e2', 'e4')" :disabled="showResultsFlag">C.维基奇</button>
    <button :class="buttonState('e4')" @click="changeScore('e4', 'e1', 'e2', 'e3')" :disabled="showResultsFlag">D.莎拉波娃</button>
  </div>
</div>

<!-- Question 7 -->
<div class="a">
  <p>7. 樊振东在比赛结束后模仿了哪位足球运动员的庆祝动作？</p>
  <div>
    <button :class="buttonState('f1')" @click="changeScore('f1', 'f2', 'f3', 'f4')" :disabled="showResultsFlag">A.姆巴佩</button>
    <button :class="buttonState('f2')" @click="changeScore('f2', 'f1', 'f3', 'f4')" :disabled="showResultsFlag">B.贝林</button>
  </div>
  <div>
    <button :class="buttonState('f3')" @click="changeScore('f3', 'f1', 'f2', 'f4')" :disabled="showResultsFlag">C. C罗</button>
    <button :class="buttonState('f4')" @click="changeScore('f4', 'f1', 'f2', 'f3')" :disabled="showResultsFlag">D.乔丹</button>
  </div>
</div>

<!-- Question 8 -->
<div class="a">
  <p>8. 潘展乐“告状”说他想和谁握手而被忽视？</p>
  <div>
    <button :class="buttonState('g1')" @click="changeScore('g1', 'g2', 'g3', 'g4')" :disabled="showResultsFlag">A.内梅特·南多尔</button>
    <button :class="buttonState('g2')" @click="changeScore('g2', 'g1', 'g3', 'g4')" :disabled="showResultsFlag">B.凯尔·查尔莫斯</button>
  </div>
  <div>
    <button :class="buttonState('g3')" @click="changeScore('g3', 'g1', 'g2', 'g4')" :disabled="showResultsFlag">C.马尔蒂尼</button>
    <button :class="buttonState('g4')" @click="changeScore('g4', 'g1', 'g2', 'g3')" :disabled="showResultsFlag">D.杰克·鲍尔</button>
  </div>
</div>

<!-- Question 9 -->
<div class="a">
  <p>9. 以下哪位没有参加男子游泳4*100米混合接力赛？</p>
  <div>
    <button :class="buttonState('h1')" @click="changeScore('h1', 'h2', 'h3', 'h4')" :disabled="showResultsFlag">A.汪顺</button>
    <button :class="buttonState('h2')" @click="changeScore('h2', 'h1', 'h3', 'h4')" :disabled="showResultsFlag">B.覃海洋</button>
  </div>
  <div>
    <button :class="buttonState('h3')" @click="changeScore('h3', 'h1', 'h2', 'h4')" :disabled="showResultsFlag">C.徐嘉余</button>
    <button :class="buttonState('h4')" @click="changeScore('h4', 'h1', 'h2', 'h3')" :disabled="showResultsFlag">D.孙佳俊</button>
  </div>
</div>

<!-- Question 10 -->
<div class="a">
  <p>10. 郑钦文说她被谁的视频激励了？</p>
  <div>
    <button :class="buttonState('i1')" @click="changeScore('i1', 'i2', 'i3', 'i4')" :disabled="showResultsFlag">A.刘翔</button>
    <button :class="buttonState('i2')" @click="changeScore('i2', 'i1', 'i3', 'i4')" :disabled="showResultsFlag">B.苏炳添</button>
  </div>
  <div>
    <button :class="buttonState('i3')" @click="changeScore('i3', 'i1', 'i2', 'i4')" :disabled="showResultsFlag">C.李娜</button>
    <button :class="buttonState('i4')" @click="changeScore('i4', 'i1', 'i2', 'i3')" :disabled="showResultsFlag">D.马龙</button>
  </div>
</div>

<!-- Question 11 -->
<div class="a">
  <p>11. 哪位中国选手在比赛中途补了一觉？</p>
  <div>
    <button :class="buttonState('j1')" @click="changeScore('j1', 'j2', 'j3', 'j4')" :disabled="showResultsFlag">A.李雯雯</button>
    <button :class="buttonState('j2')" @click="changeScore('j2', 'j1', 'j3', 'j4')" :disabled="showResultsFlag">B.侯志慧</button>
  </div>
  <div>
    <button :class="buttonState('j3')" @click="changeScore('j3', 'j1', 'j2', 'j4')" :disabled="showResultsFlag">C.罗诗芳</button>
    <button :class="buttonState('j4')" @click="changeScore('j4', 'j1', 'j2', 'j3')" :disabled="showResultsFlag">D.张雪迎</button>
  </div>
</div>

<!-- Question 12 -->
<div class="a">
  <p>12. 本届奥运中国乒乓男团获得冠军，是有史以来的奥运几连冠？</p>
  <div>
    <button :class="buttonState('k1')" @click="changeScore('k1', 'k2', 'k3', 'k4')" :disabled="showResultsFlag">A.4</button>
    <button :class="buttonState('k2')" @click="changeScore('k2', 'k1', 'k3', 'k4')" :disabled="showResultsFlag">B.5</button>
  </div>
  <div>
    <button :class="buttonState('k3')" @click="changeScore('k3', 'k1', 'k2', 'k4')" :disabled="showResultsFlag">C.6</button>
    <button :class="buttonState('k4')" @click="changeScore('k4', 'k1', 'k2', 'k3')" :disabled="showResultsFlag">D.7</button>
  </div>
</div>

<!-- Question 13 -->
<div class="a">
  <p>13. 微博id“夜玫瑰的曲”的冠军运动员是？</p>
  <div>
    <button :class="buttonState('l1')" @click="changeScore('l1', 'l2', 'l3', 'l4')" :disabled="showResultsFlag">A.盛李豪</button>
    <button :class="buttonState('l2')" @click="changeScore('l2', 'l1', 'l3', 'l4')" :disabled="showResultsFlag">B.刘宇坤</button>
  </div>
  <div>
    <button :class="buttonState('l3')" @click="changeScore('l3', 'l1', 'l2', 'l4')" :disabled="showResultsFlag">C.谢瑜</button>
    <button :class="buttonState('l4')" @click="changeScore('l4', 'l1', 'l2', 'l3')" :disabled="showResultsFlag">D.李晨</button>
  </div>
</div>

<!-- Question 14 -->
<div class="a">
  <p>14. 本届奥运最年轻的滑板运动员郑好好的年龄是？</p>
  <div>
    <button :class="buttonState('m1')" @click="changeScore('m1', 'm2', 'm3', 'm4')" :disabled="showResultsFlag">A.10岁</button>
    <button :class="buttonState('m2')" @click="changeScore('m2', 'm1', 'm3', 'm4')" :disabled="showResultsFlag">B.11岁</button>
  </div>
  <div>
    <button :class="buttonState('m3')" @click="changeScore('m3', 'm1', 'm2', 'm4')" :disabled="showResultsFlag">C.12岁</button>
    <button :class="buttonState('m4')" @click="changeScore('m4', 'm1', 'm2', 'm3')" :disabled="showResultsFlag">D.13岁</button>
  </div>
</div>

<!-- Question 15 -->
<div class="a">
  <p>15. 本届闭幕式中担任亚洲运动员代表的是？</p>
  <div>
    <button :class="buttonState('n1')" @click="changeScore('n1', 'n2', 'n3', 'n4')" :disabled="showResultsFlag">A.陈艺文</button>
    <button :class="buttonState('n2')" @click="changeScore('n2', 'n1', 'n3', 'n4')" :disabled="showResultsFlag">B.全红婵</button>
  </div>
  <div>
    <button :class="buttonState('n3')" @click="changeScore('n3', 'n1', 'n2', 'n4')" :disabled="showResultsFlag">C.孙颖莎</button>
    <button :class="buttonState('n4')" @click="changeScore('n4', 'n1', 'n2', 'n3')" :disabled="showResultsFlag">D.李冰冰</button>
  </div>
</div>

    <br />
</div>  
    </div>
</div>
    </div>
  </div>
  </template>
  
  <script>
  export default {
    name: "mtApp",
    data() {
    return {
      buttonStates: {},
      correctAnswers: {
        a2: 'a2', // 假设 'a1' 是正确答案
        z1: 'z1', // 假设 'z2' 是正确答案
        b2: 'b2',
        c2: 'c2',
        d1: 'd1',

        e1: 'e1',
        f1: 'f1',
        g2: 'g2',
        h1: 'h1',
        i1: 'i1',
        
        j3: 'j3',
        k2: 'k2',
        l3: 'l3',
        m2: 'm2',
        n3: 'n3',
      },
      showResultsFlag: false, // 标记是否展示正确答案
      isResultsVisible: false, // 新增的变量，控制结果显示
      isRestarting: false, // 新增的变量，控制是否重新开始答题
      isModalVisible: false, // 控制弹窗显示
      correctCount: 0, // 记录答对的题目数

    };
  },
    computed: {
        answeredQuestionsCount() {
            return Object.values(this.buttonStates).filter(
                (state) => state === "color-change clicked"
            ).length;
        },
        progressPercentage() {
            const totalQuestions = 15;
            return (this.answeredQuestionsCount / totalQuestions) * 100;
        },
    },
    methods: {
    changeScore(btnId1, btnId2, btnId3, btnId4) {
      if (!this.showResultsFlag) {
        this.buttonStates[btnId1] = "color-change clicked";
        this.buttonStates[btnId2] = "color-change";
        this.buttonStates[btnId3] = "color-change";
        this.buttonStates[btnId4] = "color-change";
      }
    },

    buttonState(btnId) {
      return this.buttonStates[btnId] || "color-change";
    },
    
    confirm(){
        this.isModalVisible = false; // 隐藏弹窗
        window.scrollTo({ top: 0, behavior: 'smooth' }); // 平滑滚动到顶部
    },

     // 处理点击查看结果或再来一遍
  handleProgressClick() {
    if (this.isResultsVisible) {

        this.resetQuiz();
        window.scrollTo({ top: 0, behavior: 'smooth' }); // 平滑滚动到顶部
    
    } else {
      this.showResults();
    }
  },

  // 显示结果
  showResults() {
    if(this.answeredQuestionsCount === 15)
  {
    this.isResultsVisible = true;
    this.showResultsFlag = true;

    let correctCount = 0;

// 遍历按钮状态，更新正确或错误答案
for (let btnId in this.buttonStates) {
  if (this.buttonStates[btnId] === 'color-change clicked') {
    // 如果是用户选择的选项，判断对错
    if (this.correctAnswers[btnId]) {
      this.buttonStates[btnId] = 'correct-selected'; // 正确答案
      correctCount++;
    } else {
      this.buttonStates[btnId] = 'wrong-selected'; // 错误答案
    }
  } else if (this.correctAnswers[btnId]) {
    // 如果是正确答案但未被选中
    this.buttonStates[btnId] = 'correct-answer';
  }
}

// 计算用户答对的题目数
this.correctCount = correctCount;

// 显示弹窗
this.isModalVisible = true;
}},

  // 重置答题
  resetQuiz() {
    this.isResultsVisible = false;
    this.isRestarting = false;
    this.answeredQuestionsCount = 0;
    this.showResultsFlag = false;
    this.correctCount = 0; // 重置答对题数
    // 重置按钮状态
    for (let btnId in this.buttonStates) {
      this.buttonStates[btnId] = ''; // 或者使用你初始化按钮状态的默认值
    }
  },
  

  },
  
};
  
  </script>
  
  <style scoped>


/* 弹窗的背景遮罩 */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

/* 弹窗样式 */
/* 背景覆盖层 */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* 半透明背景 */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999; /* 确保弹窗在最上层 */
}

/* 弹窗容器 */
.modal {
  background: linear-gradient(135deg, #8cff5f, #feb47b); /* 渐变背景 */
  padding: 30px 40px;
  border-radius: 15px;
  text-align: center;
  width: 350px;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
  transform: scale(0);
  animation: modalScale 0.3s ease-out forwards;
}

/* 弹窗标题 */
.modal h2 {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 15px;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 1px;
  animation: fadeIn 1s ease-out;
}

/* 弹窗内容 */
.modal p {
  font-size: 18px;
  color: #fff;
  margin-bottom: 20px;
  animation: fadeIn 1s ease-out;
}

/* 按钮样式 */
.modal button {
  background: linear-gradient(45deg, #10ffa7, #4284f5); /* 按钮渐变背景 */
  color: white;
  border: none;
  padding: 12px 25px;
  border-radius: 50px;
  cursor: pointer;
  font-size: 16px;
  font-weight: 600;
  transition: all 0.3s ease;
}

/* 按钮悬浮效果 */
.modal button:hover {
  transform: translateY(-3px); /* 上移动画 */
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
}

/* 按钮点击效果 */
.modal button:active {
  transform: translateY(1px); /* 点击时向下 */
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
}


/* 左侧图片 */
.left-image {
  width: 120px;
  height: auto;
  position: absolute;
  left: 20px;
  bottom: 45px;
  animation: fadeIn 1s ease-out;
}

/* 右侧图片 */
.right-image {
  width: 120px;
  height: auto;
  position: absolute;
  right: 20px;
  bottom: 50px;
  animation: fadeIn 1s ease-out;
}

/* 弹窗缩放动画 */
@keyframes modalScale {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}



.modal h2 {
  font-size: 28px;
  font-weight: bold;
  background: linear-gradient(45deg, #ff6f61, #f8b400);
  -webkit-background-clip: text;
  color: transparent;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
  animation: fadeIn 1s ease-out;
}

.modal p {
  font-size: 20px;
  color: #333;
  font-family: 'Arial', sans-serif;
  text-align: center;
  margin: 20px 0;
  letter-spacing: 1px;
  opacity: 0;
  animation: slideUp 1s ease-out forwards;
  color: #555;
  font-weight: 600;
}

/* 渐变背景色动画 */
@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(-10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 滑动动画 */
@keyframes slideUp {
  0% {
    opacity: 0;
    transform: translateY(10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 左右图片的视觉效果 */
.modal img {
  max-width: 80px;
  margin: 20px;
  transition: transform 0.3s ease;
}

.modal img:hover {
  transform: scale(1.1);
}


.correct-answer {
    background-color: #daa6a9;
        transform: scale(1.2);
        border: 3.5px solid rgb(0, 253, 72) !important;
        background: transparent;
        text-transform: uppercase;
        padding: 15px 50px;
        transition: transform 0.4s ease;
}

.correct-selected {
    background-color: #daa6a9;
        transform: scale(1.2);
        border: 3.5px solid rgb(0, 253, 72) !important;
        background: transparent;
        text-transform: uppercase;
        padding: 15px 50px;
        transition: transform 0.4s ease;
}

.wrong-selected {
    background-color: #daa6a9;
        transform: scale(1.2);
        border: 3.5px solid rgb(250, 2, 2) !important;
        background: transparent;
        text-transform: uppercase;
        padding: 15px 50px;
        transition: transform 0.4s ease;
}

.containerww {

  height: 10px; /* 设置容器高度 */
}

.top-right-image1 {
  position: absolute;
  top: 100px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
  animation: float 3s ease-in-out infinite;

}
.top-right-image2 {
  position: absolute;
  top: 600px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image3 {
  position: absolute;
  top: 1100px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image35 {
  position: absolute;
  top: 1500px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image4 {
  position: absolute;
  top: 1500x; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image5 {
  position: absolute;
  top: 2010px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image6 {
  position: absolute;
  top: 2500px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image7 {
  position: absolute;
  top: 3000px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image8 {
  position: absolute;
  top: 3520px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image9 {
  position: absolute;
  top: 4000px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image10 {
  position: absolute;
  top: 4490px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image11 {
  position: absolute;
  top: 5000px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image12 {
  position: absolute;
  top: 5500px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-right-image13 {
  position: absolute;
  top: 6000px; /* 距离顶部10px */
  right: 10px; /* 距离右侧10px */
  width: 200px; /* 设置图片的宽度 */
  height: auto; /* 保持比例 */
}

.top-left-image1 {
  position: absolute;
  top: 0px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image2 {
  position: absolute;
  top: 400px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image3 {
  position: absolute;
  top: 800px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image4 {
  position: absolute;
  top: 1200px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image5 {
  position: absolute;
  top: 1710px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image6 {
  position: absolute;
  top: 2200px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image7 {
  position: absolute;
  top: 2700px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image8 {
  position: absolute;
  top: 3220px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image9 {
  position: absolute;
  top: 3700px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image10 {
  position: absolute;
  top: 4190px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image11 {
  position: absolute;
  top: 4700px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image12 {
  position: absolute;
  top: 5200px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}

.top-left-image13 {
  position: absolute;
  top: 5700px; /* top值减去300px */
  left: 10px; /* 修改为left */
  width: 200px;
  height: auto;
}



h1 {
    display: flex;
    justify-content: center;
    color: #e5e5e5;
    font-family: eva;
    font-size: 50px;
    background: linear-gradient(45deg, #ff6347, #1e90ff);
    -webkit-background-clip: text;
    background-clip: text;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.5);
    animation: float 3s ease-in-out infinite;
}

@keyframes float {
    0% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0); }
}

#shiny-shadow {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background: #1c2541;
}

.color-change {
    &.clicked {
        background-color: #daa6a9;
        transform: scale(1.2);
        border: 3.5px solid black;
        background: transparent;
        text-transform: uppercase;
        padding: 15px 50px;
        transition: transform 0.4s ease;
    }
}

.test {
    font-family: maiyuan;
    display: flex;
	margin: 0 auto;
	flex-wrap: wrap;
	flex-direction: column;
	max-width: 70%;
	position: relative;
    font-size: 27px;
    font-weight: 600;
    text-align: center;
}

.a {
    padding: 50px;
    margin: 40px;
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    align-items: center;
    justify-content: center;
    button {
        margin: 20px 70px 10px;
        border: 3.5px solid black;
        width:290px ;
        background: transparent;
        text-transform: uppercase;
        color: black;
        padding: 15px 50px;
        outline: none;
        overflow: hidden;
        position: relative;
        font-family: maiyuan;
        font-weight: 500;
        font-size: 25px;
        background: rgba(255, 255, 255, 0.25);
        box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
        backdrop-filter: blur(4px);
        -webkit-backdrop-filter: blur(4px);
        border-radius: 10px;
        border: 1px solid rgba(255, 255, 255, 0.18);
        &:hover:after {
            left: 120%;
            transition: all 600ms cubic-bezier(0.3, 1, 0.2, 1);
        }

        &:after {
            content: "";
            display: block;
            position: absolute;
            top: -36px;
            left: -100px;
            background: rgb(255, 255, 255);
            width: 70px;
            height: 125px;
            opacity: 20%;
            transform: rotate(-45deg);
        }
    }
}

.progress-container {
    position: fixed;
    width: 10em;
    height: 10em;
    margin: 20px auto;
    z-index: 99;
    left: 1em;
    .progress-circle {
        transform: rotate(-90deg);
        width: 100%;
        height: 100%;

        .circle-bg {
            fill: none;
            stroke: #eee;
            stroke-width: 3.8;
        }

        .circle {
            fill: none;
            stroke-width: 2.8;
            stroke-linecap: round;
            stroke: #03e9f4;
            transform: rotate(-90deg);
            transform-origin: 50% 50%;
        }
    }

    .progress-text {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 20px;
        font-weight: bold;
        white-space: nowrap;
    }
}

  :root {
    --background-color: #2c3e50;
    --border-color: #7591AD;
    --text-color: #34495e;
    --color1: #EC3E27;
    --color2: #fd79a8;
    --color3: #0984e3;
    --color4: #00b894;
    --color5: #54bfb8;
    --color6: #e056fd;
    --color7: #F97F51;
    --color8: #BDC581;
  }
  

  

  
  .all {

    background-color: var(--color5); /* 保留原来的颜色设置作为备用 */
  background-image: url('/src/assets/1.jpg'); /* 添加图片背景 */
  background-size: cover; /* 让图片完全覆盖背景 */
  background-position: center center; /* 让图片居中显示 */
  position: relative;
  background-attachment: fixed; /* 确保背景随页面滚动 */
    font-family: 'Montserrat', sans-serif, Arial, 'Microsoft Yahei';
  }
  
  .container {
    position: relative;
    width: 100vw;

    overflow: hidden;
    
  }
  
  .bubble {
    position: fixed;
    width: 40px;
    height: 40px;
    background-color: #fff;
    bottom: 0;
    opacity: 0.6;
    border-radius: 100%;
    animation: flying 3s ease-in-out infinite;
  }
  
  .bubble:nth-child(3n+1) {
    left: calc(90px * var(--i));
    width: calc(3px * var(--i));
    height: calc(3px * var(--i));
    animation-duration: calc(0.3s * var(--i));
  }
  
  .bubble:nth-child(3n+2) {
    left: calc(50px * var(--i));
    width: calc(4px * var(--i));
    height: calc(4px * var(--i));
    animation-duration: calc(0.5s * var(--i));
  }
  
  .bubble:nth-child(3n+3) {
    left: calc(20px * var(--i));
    width: calc(2px * var(--i));
    height: calc(2px * var(--i));
    animation-duration: calc(0.4s * var(--i));
  }
  
  @keyframes flying {
    0% {
        bottom: -50px;
        transform: translateX(0px) translateY(0px); /* 从页面外开始 */
    }
    25% {
        transform: translateX(20px) translateY(-50px); /* 上移 */
    }
    50% {
        transform: translateX(100px) translateY(100px); /* 右下方漂浮 */
    }
    75% {
        transform: translateX(130px) translateY(-100px); /* 继续漂浮 */
    }
    100% {
        bottom: 900px;
        transform: translateX(-10px) translateY(200px); /* 向下漂浮 */
    }
  }
  </style>