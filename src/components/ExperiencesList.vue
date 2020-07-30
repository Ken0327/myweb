<template>
  <div class="experience text-left spaceWrapperContainer">
    <div id="experience" class="spaceWrapper"></div>
    <h1 class="title">{{ title }}</h1>
    <h2 class="subTitle">{{ subTitle }}</h2>
    <div class="">
      <ul class="ul-list">
        <li class="item ul-list-item wow slideInUp" v-for='item in experiences' :key='item.index'>
          <h5>{{ item.title }} | {{ item.during }}</h5>
          <h6>{{ item.company }}</h6>
          <ul class="ul-list--inner">
            <li class="item" v-for='listitem in item.list' :key='listitem.index'>
              {{ listitem }}
            </li>
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
  name: 'ExperiencesList',
  props: ['title', 'subTitle'],
  data () {
    return {
      experiences: [
        {
          company: '台灣國際航電 Garmin',
          title: '工程師',
          during: '2016/7-Now',
          list: [
            '• MES製程整合',
              '1.工廠生產線導入Traceabulity設備和系統，應用於雷雕機和條碼機',
              '2.開發測試和資料轉拋系統，撰寫Web API串接和轉拋至SQL資料庫',
            '• IOT軟體開發',
              '1.協助開發自動鎖螺絲機設備，撰寫MPU人機介面、資料轉拋系統',
              '2.開發IOT將設備數位化，撰寫MPU網頁前後端，透過MQTT、Kafka串接裝置、API轉拋資料',
              '3.開發設備Burn In Chamber烤箱，應用於製程高溫測試，整合自動化測試',
            '• 製程測試優化',
              '1.開發測試良率分析工具',
              '2.協助開發測試分析網頁',
              '3.跨部門合作，導入BMW車機OEM量產測試'
          ]
        }
      ]
    }
  }
}
</script>
