<template>
  <div class="contact mb-1">
    <div class="position-relative">
      
      <div class="bg-img" :style="{backgroundImage: 'url(' + imgBg + ')' }">
        <img :src="imgBg" alt="">
        <div class="bg-cover"></div>
      </div>
      <div class="contact-data">
        <h1 class="p-4 position-absolute col-md-3 mx-auto"><img :src="imgLogo2" alt=""></h1>
        <div class="row">
          <div class="col-md-6">
            <div class="row justify-content-start">
              <div v-for="(item, index) in contact" :key="item.index">
                <span class="mr-2 d-inline-block p-4">
                  <font-awesome-icon :icon="item.icon"/>
                  {{ item.data }}
                </span>
                <b class="dot mr-2" v-if="index === 0"><font-awesome-icon icon="circle" /></b>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="bg-img bg-img--mask" :style="{maskImage: 'url('+ mask +')'}">
      </div>
    </div>
    <div class="contact-data">
      <div class="bg-img bg-img--me" :style="{backgroundImage: 'url(' + imgMe + ')' }"></div>
      
        <div class="bg-img bg-img--big bg-img--me" :style="{backgroundImage: 'url(' + img + ')' }">
      </div>
      <div class="contact-data--me col-md-5">
        <h1 class="p-4">{{ msg }}</h1>
        <div class="row justify-content-start">
          <div v-for="(item, index) in contact" :key="item.index">
            <span class="mr-2 d-inline-block p-4">
              <font-awesome-icon :icon="item.icon"/>
              {{ item.data }}
            </span>
            <b class="dot mr-2" v-if="index === 0"><font-awesome-icon icon="circle" /></b>
          </div>
        </div>
      </div>
    </div>
    <div class="container-fluid">
      <div class="row">
        <div class="bg-img bg-img--me col-md-6" :style="{backgroundImage: 'url(' + img + ')' }">
        </div>
        <div class="col-md-6">
          <h1 class="p-4">{{ msg }}</h1>
          <div class="row justify-content-start">
            <div v-for="(item, index) in contact" :key="item.index">
              <span class="mr-2 d-inline-block p-4">
                <font-awesome-icon :icon="item.icon"/>
                {{ item.data }}
              </span>
              <b class="dot mr-2" v-if="index === 0"><font-awesome-icon icon="circle" /></b>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ImgMe from '../assets/images/ken1.jpg'
import ImgMask from '../assets/images/img_mask.svg'
import ImgPicBg from '../assets/images/header-bg.jpg'
import ImgLogo2 from '../assets/images/logo-ken2.png'

export default {
  name: 'Contact',
  props: {
    msg: String
  },
  data () {
    return {
      imgMe: ImgMe,
      mask: ImgMask,
      imgBg: ImgPicBg,
      imgLogo2: ImgLogo2,
      contact: [
        {
          icon: 'mobile-alt',
          data: '0912968315'
        },
        {
          icon: 'envelope',
          data: 'dr.k0327@gmail.com'
        }
      ],
      links: [
        {
          iconName: 'github',
          link: 'https://github.com/ken0327'
        },
        {
          iconName: 'codepen',
          link: 'https://codepen.io/ken0327/'
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
@import "@/assets/scss/base/_variables.scss";

.contact {
  height: $font4*100;
  // background-color: $mango;
  // position: relative;
  // .contact-data {
  //   position: absolute;
  //   margin: auto;
  //   right: 0;
  //   top: 0;

  //   &--me {
  //     position: absolute;
  //     margin: 0;
  //     right: 0;
  //     top: 0;
  //     bottom: 0;
  //   }
  // }
}
</style>
