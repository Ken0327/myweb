<template>
  <div class="skill section section-bg spaceWrapperContainer">
    <div id="skill" class="spaceWrapper"></div>
    <div class="container">
    <h1 class="title">{{ title }}</h1>
    <h2 class="subTitle">{{ subTitle }}</h2>
      <div class="row my-4">
        <div class="col-md-6 mb-4 wow bounceIn animated" v-for="(item) in skills" :key='item.index'>
          <div class="skill-item">
            <span class="icon d-inline-block mb-3">
              <font-awesome-icon :icon="item.icon"/>
            </span>
            <h4 class="skill-item-title font-weight-bold">{{ item.title }}</h4>
            <p class="line-s my-2 mx-auto"></p>
            <h6 class="my-3">
              <span class="mx-1 d-inline-block" v-for="(skillItem, index) in item.skillList" :key='skillItem.index'>
                {{ skillItem }}
                {{ (index + 1 &lt; skillItem.length) ? ', ' : '' }}
              </span>
            </h6>
            <div class="skill-item-text">
              <ul class="ul-list ul-list--none">
                <li class="item ul-list-item" v-for="listItem in item.info" :key="listItem.index">
                  {{ listItem }}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  props: {
    title: String,
    subTitle: String
  },
  data () {
    return {
      striped: true,
      animate: true,
      skills: [
        {
          icon: 'desktop',
          title: 'Full Stack Development',
          skillList: ['HTML5', 'CSS3', 'JavaScript(ES6)', 'Vue.js', 'Node.js', 'Python', 'MongoDB', 'MySQL'],
          info: [
            '使用 HTML5、CSS3 獨立切版或套用 Bootstrap',
            // '搭配 JavaScript 或 jQuery 製作各式動畫效果',
            // '熟悉 Liquid 語法，開發各種樣版或新功能、新畫面',
            // '以 Ajax 串接 API 資料',
            '使用 Vue.js 建置網頁前端',
            '使用 Node.js, MongoDB, MySQL 建置資料庫和後台串接API'
          ]
        },
        {
          icon: 'server',
          title: 'MES System',
          skillList: ['C#', '.NET Framework', '.NET Core', 'MSSQL', 'MYSQL'],
          info: [
            '建立 .NET Framework Web API 串接資料庫',
            '使用 C# 開發測試程式、測試分析工具',
          ]
        },
        {
          icon: 'palette',
          title: 'IOT Embedded ',
          skillList: ['C/C++', 'Python', 'MQTT', 'Kafka'],
          info: [
            '使用 C++ 開發MCU',
            '使用 Python 在 inux 環境開發 MPU GUI和後端',
            '透過 MQTT、Kafka和Web API串接資料'
          ]
        },
        {
          icon: 'terminal',
          title: 'Others',
          skillList: ['Git', 'Linux'],
          info: [
            '熟悉 Git 常用的基本指令',
            '熟悉 Linux 環境和指令',
          ]
        }
      ],
      webSkill: [
        {
          item: 'HTML5, CSS3',
          data: 95
        },
        {
          item: 'SCSS',
          data: 80
        },
        {
          item: 'Bootstrap',
          data: 85
        },
        {
          item: 'Javascript',
          data: 75
        },
        {
          item: 'jQuery',
          data: 90
        },
        {
          item: 'Vue.js',
          data: 40
        },
        {
          item: 'Node.js',
          data: 5
        },
        {
          item: 'Webpack',
          data: 25
        }
      ],
      language: [
        '中文 / 台語 精通', '英文 (TOEIC 785)'
      ]
    }
  },
  computed: {
    webSkillGroups () {
      return Array(this.webSkill.length / 3).fill().map((_, i) => [this.webSkill[i * 2], this.webSkill[i * 2 + 1]])
    }
  },
  methods: {
  }
}
</script>
