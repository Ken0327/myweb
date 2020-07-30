<template>
  <div class="education text-left spaceWrapperContainer">
    <div id="education" class="spaceWrapper"></div>
    <h1 class="title">{{ title }}</h1>
    <h2 class="subTitle">{{ subTitle }}</h2>
    <div class="exp-special">
      <ul class="ul-list">
        <li class="item ul-list-item wow slideInUp" v-for='item in education' :key='item.index'>
          <h5>{{ item.department }} | {{ item.during }}</h5>
          <h6>{{ item.title }}</h6>
          <ul class="ul-list--inner">
            <li class="item" v-for='list in item.about' :key='list.index'>{{ list }}</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/base/_variables.scss";
</style>
<script>
export default {
  name: 'Education',
  props: ['title', 'subTitle'],
  data () {
    return {
      education: [
        {
          title: '國立清華大學',
          during: '2012/9-2015/1',
          department: '工程與系統科學研究所',
          about: [
            '• 研究領域: 微機電系統(MEMS)，撰寫LabVIEW應用於控制系統和機器人，Matlab軟體用於數值運算和分析、繪圖、影像處理和曲線擬合，應用於實驗的系統控制和COMSOL模擬',
            '• 論文題目: 利用時變電場即時操控次微米液滴生成之研究 Electric-Field Induced Tip Streaming for Sub-Femtoliter Droplet Formation on Deman',
            '• 期刊發表: ',
            '[1]Electric-field triggered, on-demand formation of sub-femtoliter droplets				2018/01/04 Elsevier/Journal/Sensors and Actuators B: Chemical',
            '[2]Electric-field triggered tip streaming for on demand sub-femtoliter droplet formation			2015 MicroTAS 2015/19th International Conference on Miniaturized Systems for Chemistry and Life Sciences'
          ]
        },
        {
          title: '國立嘉義大學',
          during: '2008/9-2012/6',
          department: '電子物理系',
          about: [
            '• 主修電磁學、電子學、量子物理、嵌入式系統、電腦輔助繪圖'
          ]
        }
      ]
    }
  }
}
</script>
