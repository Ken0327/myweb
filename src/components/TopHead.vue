<template>
  <div>
    <div id="nav" class="fixed-top" :class="{ active: isActive }">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
    <div class="topHead fixed-top">
      <div class="topHead-sticky container-fluid p-0">
        <ul class="d-flex justify-content-between mb-0">
          <li class="topHead-item topHead-item--left">
            <a><font-awesome-icon icon="envelope" /></a>
          </li>
          <li class="topHead-item">
            <router-link class="logo" to="/">
              <img :src="imgLogoS" alt="Ken's Vue">
            </router-link>
          </li>
          <li class="topHead-item topHead-item--right">
            <a @click="isActive = !isActive"><font-awesome-icon icon="ellipsis-h" /></a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
    <!-- <header>
      <ul>
        <li>
          <a href="mailto:dr.k0327@gmail.com" class="mail">
            <font-awesome-icon icon="envelope" />
          </a>
        </li>
        <li>
          <a href="index.html">
            <img :src="imgLogo" alt="">
          </a>
        </li>
        <li>
          <div class="nav">
            <font-awesome-icon icon="ellipsis-h" />
          </div>
        </li>
      </ul>
    </header> -->
    <!-- <div class="position-sticky sticky-top d-none">
      <div class="topHead-sticky container-fluid p-0">
        <ul class="d-flex justify-content-between mb-0">
          <li class="topHead-item topHead-item--left">
            <a><font-awesome-icon icon="envelope" /></a>
          </li>
          <li class="topHead-item">
            <router-link class="logo" to="/">
              <img src="@/assets/images/logo-5.png" alt="Ken's Vue">
            </router-link>
          </li>
          <li class="topHead-item topHead-item--right">
            <a><font-awesome-icon icon="ellipsis-h" /></a>
          </li>
        </ul>
      </div>
      <div class="sideMenu row justify-content-md-center">
        <div class="logo logo col-md-2 mb-4">
          <img alt="Vue logo" src="@/assets/images/logo-ken.png">
        </div>
      </div>
      <div id="nav">
        <router-link to="/">
          <img src="@/assets/images/logo-web.png" alt="Ken's Vue">
        </router-link> |
        <router-link to="/about">About</router-link> |
        <router-link to="/todo">Todo List</router-link>
      </div>
    </div> -->

<script>
import ImgLogo from '../assets/images/logo-ken.png'
import ImgPicBg from '../assets/images/header-bg.jpg'
import ImgLogoS from '../assets/images/logo-s.png'

export default {
  name: 'TopHead',
  data () {
    return {
      isActive: false,
      imgLogo: ImgLogo,
      imgBg: ImgPicBg,
      imgLogoS: ImgLogoS,
      logo: '../assets/images/logo-web.png',
      icons: ['bars', 'envelope'],
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
      worksLink: [
        {
          iconName: 'github',
          link: 'https://github.com/ken0327'
        },
        {
          iconName: 'codepen',
          link: 'https://codepen.io/Ken/'
        },
        {
          iconName: 'linkedin',
          link: 'https://www.linkedin.com/in/ken-chen-8725aa86/'
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
@import "@/assets/scss/base/_variables.scss";

#nav {
  padding: 5rem 0 2.5rem;
  background-color: rgba(darken($dark-grey, 30%), 0.5);
  top: -100%;
  -webkit-transition: all .3s ease-in-out;
  -moz-transition: all .3s ease-in-out;
  transition: all .3s ease-in-out;

  a {
    font-weight: bold;
    color: $white;
    -webkit-transition: all .3s ease;
    -moz-transition: all .3s ease;
    transition: all .3s ease;

    &.router-link-exact-active {
      color: $white;
    }
    &:hover {
      font-size: 1.5rem;
    }
  }

  &.active {
    top: 0;
  }
}
.topHead {
  width: 100%;
  height: $font4*11;
  background-color: $white;

  &-sticky {
    box-shadow: 0px -1px $font4*2 rgba(0,0,0,0.2);
  }
  .topHead-item {
    min-width: $font4*11;
    height: $font4*11;
    line-height: $font4*11;
    font-size: $font4*6;
    color: $dark-grey;
    a {
      &:hover {
        background-color: darken($dark-grey, 10%);
        color: $white;
      }
      &.active {
        i {
          transform: rotate(90deg);
        }
      }
    }
  }

  &-sticky {
    .logo {
      height: $font4*11;
      padding: $font4 0;

      img {
        height: 100%;
        width: auto;
        vertical-align: top;
      }
    }
  }

  &-data {
    .logo {
      img {
        max-width: 22rem;
        min-width: 18rem;
      }
    }
    .icon {
      width: 1rem;
      height: 1rem;
    }
  }
}

.waypoint {
  height: 500px;
  background: #420983;
}
.waypoint p {
  background: #42b983;
  margin: 3px;
}

.sideMenu {
    display: none;
}
</style>
