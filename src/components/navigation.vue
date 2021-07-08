<template>
  <header class="dropdown" @click="toggleMobileNav()">
    <nav>
      <div class="nav__title">
        <div class="nav__title-icon">
          <fa class="icon" :icon="['fas', 'arrow-down']" />
        </div>
        <div class="nav__title-text">
          <img src="../assets/img/Group134.png" alt="navigation" />
        </div>
        <div class="nav__title-x">
          <button><img src="../assets/img/Group136.png" alt="x" /></button>
        </div>
      </div>
      <ul>
        <li>
          <button @click="aboutComponent" ><span class="nav-span">ჩვენს შესახებ</span></button>
        </li>
        <li>
          <button @click="rightsComponent()"><span class="nav-span">წესები და პირობები</span></button>
        </li>
        <li>
          <button @click="confidencialComponent"><span class="nav-span">კონფიდენციალურობა</span></button>
        </li>
        <li>
          <button @click="contactComponent"><span class="nav-span">საკონტაქტო ინფორმაცია</span></button>
        </li>
      </ul>
      <div class="nav-animation"></div>
      <div class="nav__buttons">
        <button
          @click="handleCompany()"
          class="nav__buttons-button"
        >
          <span>კომპანიები</span>
        </button>
        <button
          @click="handleCourier()"
          class="nav__buttons-button"
        >
          <span>კურიერები</span>
        </button>
      </div>
    </nav>
  </header>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  props: {
    activetabs: Object,
    rightsComponent: Function,
    confidencialComponent: Function,
    contactComponent: Function,
    aboutComponent: Function,
    handleCompany:Function,
    handleCourier:Function,
    toggleMobileNav: Function
  },
  setup(props) {
    console.log(props.toggleMobileNav);
    
    const dropdown = ref();
    
    return {
    dropdown
    };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/main.scss";

.dropdown {
  display: flex;
  flex-direction: column;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  max-width: 250px;
  height: 100%;
  background-color: $black;
  color: $orange;
  padding: 60px 20px;
  ul {
    padding: 38px 0;
  }
}
.nav__title {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 20px;
  &-icon {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background-color: $orange;
    color: $black;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
.nav-span{
    color:$orange;
    transition: 0.5s;
    &:hover{
        color: #fff;
    }
}
.nav-animation{
    width: 100%;
    height: 30px;
    background-image: url("../assets/img/Group147.png");
    background-position: center;
    background-size: auto 100%;
    background-repeat: no-repeat;
    animation: moveBg 10s linear infinite;
}
.nav__buttons{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 100%;
    height: 200px;
    padding: 40px 0;

    &-button{
        width: 100%;
      height: 46%;
      background-color: transparent;
      color: #fff;
      position: relative;
      border: 3px solid #fff;
      &::before {
          content: "";
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          z-index: -1;
          background-color: #fff;
          transition: transform 300ms ease-in-out;
          transform: scaleX(0);
          transform-origin: right;
        }
        &:hover::before {
          transform: scaleX(1);
        }
        &:focus::before {
          transform: scaleY(1);
        }
        &:hover {
          span {
            color: $black;
          }
        }
        &:focus {
          span {
            color: $black;
          }
        }
    }
}
</style>
