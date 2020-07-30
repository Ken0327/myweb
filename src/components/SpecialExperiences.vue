<template>
  <div>
    <h2> {{ title }}</h2>
    <div class="exp-special">
      <div class="exp-special-list" v-for='item in specialExperience' :key='item.index'>
        <img :src="item.img" :alt="item.item">
        <h5>{{ item.title }}</h5>
        <p class="during">{{ item.during }}</p>
      </div>
    </div>
  </div>
</template>

<script>
// import ImgCanada from '../assets/images/canada_northernlight.jpg'
export default {
  name: 'SpecialExperiences',
  props: ['title'],
  data () {
    return {
      specialExperience: [
        {
          // title: '加拿大打工度假',
          // during: '2012/4-2013/2',
          // img: ImgCanada
        }
      ]
    }
  }
}
</script>
