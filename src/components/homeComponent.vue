<template>
  <div class="header">
    <div class="header__background">
      <div class="nav">
        <div class="nav__button">
          <button
            @click="toggleMobileNav"
            v-show="burger.mobile"
            :class="{ 'icon-active': burger.mobileNav }"
          >
            <img src="../assets/img/Group150.png" alt="nav" />
          </button>
        </div>
        <transition name="mobile-animation">
          <navigation
            v-show="burger.mobileNav"
            :activetabs="activetabs"
            :rightsComponent="rightsComponent"
            :confidencialComponent="confidencialComponent"
            :contactComponent="contactComponent"
            :aboutComponent="aboutComponent"
            :handleCompany="handleCompany"
            :handleCourier="handleCourier"
            :toggleMobileNav="toggleMobileNav"
          />
        </transition>
      </div>

      <div class="buttons">
        <button @click="handleCompany()" class="btn btn-company">
          <p>კომპანიები</p>
        </button>
        <button @click="handleCourier()" class="btn btn-rights">
          <p>კურიერები</p>
        </button>
      </div>
    </div>
  </div>
  <div class="home__body">
    <div class="home__body-title body-both">
      <img src="../assets/img/Group119.png" alt="title" />
    </div>

    <div class="home__body-slogan body-both">
      <img src="../assets/img/Group85.png" alt="slogan" />
    </div>

    <div class="home__body__right body-both">
      <div class="home__body__right-video">
        <video class="video" autoplay loop muted>
          <source src="../assets/video/MOT2video.mp4" type="video/mp4" />
        </video>
      </div>
      <div class="onvideo-animation"></div>
    </div>

    <div class="home__body-download body-both">
      <div class="home__body-download-wrapper">
        <button @mouseleave="mouseOver('.downloadA')" class="download-one">
          <a class="downloadA" href="#"
            ><img src="../assets/img/Component2.png" alt="download"
          /></a>
        </button>
        <button @mouseleave="mouseOver('.downloadB')" class="download-one">
          <a class="downloadB" href="#"
            ><img src="../assets/img/Component2.png" alt="download"
          /></a>
        </button>
      </div>
      <div class="download-three">
        <a href="#"><img src="../assets/img/Group1.png" alt="download"/></a>
      </div>
    </div>
  </div>
  <div class="home__bottom"></div>
</template>

<script>
import { reactive } from "@vue/reactivity";
import navigation from "../components/navigation.vue";
import { onBeforeMount, onUnmounted } from "@vue/runtime-core";
export default {
  components: {
    navigation,
  },
  props: {
    handleCompany: Function,
    activetabs: Object,
    handleCourier: Function,
    scroll: Function,
    rightsComponent: Function,
    confidencialComponent: Function,
    contactComponent: Function,
    aboutComponent: Function,
  },
  setup() {
    const mouseOver = (comp) => {
      document.querySelector(comp).classList.add("mouseover");
    };

    const burger = reactive({
      mobileNav: null,
      mobile: null,
      windowWidth: null,
    });
    const toggleMobileNav = () => {
      burger.mobileNav = !burger.mobileNav;
    };
    const checkScreen = () => {
      burger.windowWidth = window.innerWidth;
      if (burger.windowWidth <= 1024) {
        burger.mobile = true;
        return;
      }
      burger.mobile = false;
      burger.mobileNav = false;
      return;
    };
    onBeforeMount(() => {
      window.addEventListener("resize", checkScreen);
      checkScreen();
    });
    onUnmounted(() => {
      window.removeEventListener("resize", checkScreen);
      checkScreen()
    });

    return { mouseOver, burger, toggleMobileNav, checkScreen };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/main.scss";
@import "../assets/scss/fonts/fonts.scss";

.header {
  width: 100%;
  height: 80px;
  border-bottom: 1px solid black;
  &__background {
    background-image: url("../assets/img/headeranim.png");
    background-position: center;
    background-size: 150% auto;
    background-repeat: no-repeat;
    width: 100%;
    height: 80px;
    animation: moveBg 30s linear infinite;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    position: relative;
    .nav {
      position: absolute;
      top: 0;
      left: 0;
      &__button {
        width: 115px;
        height: 115px;
        display: flex;
        align-items: center;
        justify-content: center;
        button{
          img{
            width: 60px;
            height: 60px;
          }
        }
        .icon-active {
          transform: rotate(180deg);
        }
      }
    }
    .btn {
      width: 382px;
      height: 80px;
      background-color: $black;
      color: $orange;
      position: relative;
      &::before {
        content: "";
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        width: 100%;
        height: 3px;
        background-image: url("../assets/img/Group111.png");
        background-position: center;
        transition: transform 300ms ease-in-out;
        transform: scale(0);
        animation: moveBg 30s linear infinite;
      }
      &:hover::before {
        transform: scale(1);
      }
      &:hover {
        color: #fff;
      }
    }
    .btn-company {
      clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
      position: absolute;
      top: 0;
      right: 201px;
    }
    .btn-rights {
      clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
      position: absolute;
      top: 0;
      right: -95px;
    }
  }
}

.home__body {
  width: 100%;
  height: 80vh;
  display: grid;
  grid-template-columns: 60% 40%;
  grid-template-rows: 65% 15% 20%;
  padding: 60px 0px;
  .body-both {
    width: 100%;
    height: 100%;
  }
  &-title {
    grid-column-start: 1;
    grid-row-start: 1;
    padding: 40px 80px 20px 120px;
    img {
      width: 100%;
      height: 90%;
    }
  }
  &-slogan {
    grid-column-start: 1;
    grid-row-start: 2;
    padding-left: 120px;
    img {
      width: 50%;
      height: 70%;
    }
  }
  &__right {
    grid-column-start: 2;
    grid-row-start: 1;
    grid-row-end: 4;
    position: relative;
    &-video {
      height: 100%;
      width: 100%;
      border-radius: 30px 0px 0px 30px;
      border: 4px solid $black;
      position: absolute;
      right: 0;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      video {
        height: 100%;
        border-radius: 30px 0px 0px 30px;
      }
    }
    .onvideo-animation {
      position: absolute;
      bottom: 100px;
      right: 0;
      height: 50px;
      width: 70%;
      background-image: url("../assets/img/Group111.png");
      animation: moveBg 7s linear infinite;
      background-repeat: no-repeat;
      background-size: auto 100%;
    }
  }
  &-download {
    grid-column-start: 1;
    grid-row-start: 3;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
    height: 100%;
    padding: 0px 120px;
    &-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-around;
      width: 100%;
      height: 70%;
    }
    .download-one {
      background-color: transparent;
      width: 50%;
      height: 100%;
      a {
        display: inline-block;
        border-radius: 30px;
        transition: 0.5s;
        background-image: url("../assets/img/Component2icon.png");
        background-position: center;
        background-size: 100% 100%;
        background-repeat: no-repeat;
        width: 100%;
        height: 100%;

        &:hover {
          background-color: #fff;
          animation: iconAnim 0.3s;
        }
      }
      img {
        width: 100%;
        height: 100%;
      }
    }
    .download-three {
      img {
        width: 90%;
        height: 100%;
        padding-left: 60px;
        padding-top: 10px;
      }
    }
  }
}
.mouseover {
  animation: iconAnimReverse 0.3s reverse;
}

.home__bottom {
  width: 90%;
  height: 50px;
  background-image: url("../assets/img/Group69.png");
  animation: moveBg 10s linear infinite;
  background-repeat: no-repeat;
  background-size: auto 100%;
}

.mobile-animation-enter-active, 
.mobile-animation-leave-active {
  transition: 1s ease all;
}
.mobile-animation-enter-from,
.mobile-animation-leave-to{
  transform:translateX(-250px);
}
.mobile-animation-enter-to{
  transform:translateX(0);
}
</style>
