<template>
  <div class="aboutMe section spaceWrapperContainer">
    <div id="about" class="spaceWrapper"></div>
    <div class="container">
      <div class="row">
          <div class="col-xs-12 col-md-6">
              <div class="about-content text-left">
                <h1 class="title mb-2">{{ title }}</h1>
                <h2 class="subTitle">I'm Ken Chen / 陳義明</h2>
                <p class="my-2">I am a Software/Firmware Engineer from Taiwan.</p>
                <p class="my-2 description">在電子廠擔任軟體工程師，從事製程測試和軟韌體開發超過四年。熟悉 C/C++、C#、Python、SQL、Linux、Javascript、HTML、等相關技術。平常喜歡瞭解科技新知、新技術，並應用在工作或生活。休閒興趣是唱歌、音樂、旅行、攝影、爬山。</p>
                <ContactMe></ContactMe>
                <SocialMedia></SocialMedia>
              </div>
          </div>
          <div class="col-xs-12 col-md-6">
          </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import "@/assets/scss/base/_variables.scss";
.about-content {
  p {
    color: darken($light-grey, 25%);
  }
}
</style>

<script>
import ContactMe from '@/components/ContactMe.vue'
import SocialMedia from '@/components/SocialMedia.vue'
export default {
  props: ['title'],
    components: {
      ContactMe, SocialMedia
  }
}
</script>
