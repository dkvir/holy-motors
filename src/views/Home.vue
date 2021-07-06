<template>
  <div class="home for-all-components">
    <homeComponent
      :scroll="scroll"
      :handleCourier="handleCourier"
      :handleCompany="handleCompany"
      :activetabs="activetabs"
    />
  </div>
  <div class="lookingfor for-all-components">
    <div class="lookingfor__wrapper">
      <div class="lookingfor__wrapper-header all-lookingfor-wrappers">
        <div class="lookingfor__wrapper-header-img">
          <div class="lookingfor__wrapper-header-img-inner"></div>
        </div>
      </div>
      <div class="lookingfor__wrapper-title all-lookingfor-wrappers">
        <h3>
          პარტნიორ კომპანიებსა და კურიერებს, რომლებიც ჩვენთან ერთად
          დაამკვიდრებენ სერვისის შეუდარებელ სტანდარტს.
        </h3>
      </div>
      <div class="lookingfor__wrapper-buttons all-lookingfor-wrappers">
        <button
          @click="handleCompany()"
          class="lookingfor__wrapper-buttons-button"
        >
          <span>კომპანიები</span>
        </button>
        <button
          @click="handleCourier()"
          class="lookingfor__wrapper-buttons-button"
        >
          <span>კურიერები</span>
        </button>
      </div>
    </div>
    <div class="lookingfor__components">
      <transition name="fade">
        <companyComponent
          v-if="activetabs.companyComponent"
          class="companyComponent"
        />
      </transition>
      <transition name="fade">
        <courierComponent
          v-if="activetabs.courierComponent"
          class="companyComponent"
        />
      </transition>
    </div>
    <div class="lookingfor__hr"></div>
  </div>
  <div class="about for-all-components">
    <transition name="fadeUp"> 
      <component class="footerComponent" :is="activetabs.footerComponent" />
    </transition>
    <div class="about__buttons">
       <button
          @click="rightsComponent()"
          class="lookingfor__wrapper-buttons-button about__buttons-btn "
        >
          <span>წესები და პირობები</span>
        </button>
         <button
          @click="confidencialComponent()"
          class="lookingfor__wrapper-buttons-button about__buttons-btn  "
        >
          <span>კონფიდენციალურობა</span>
        </button>
         <button
          @click="contactComponent()"
          class="lookingfor__wrapper-buttons-button about__buttons-btn"
        >
          <span>საკონტაქტო ინფორმაცია</span>
        </button>
    </div>
  </div>
</template>

<script>
import homeComponent from "../components/homeComponent.vue";
import companyComponent from "../components/companyComponent.vue";
import courierComponent from "../components/courierComponent.vue";
import { reactive } from "@vue/reactivity";
import aboutComponent from "../components/aboutComponent.vue";
import rightsComponent from "../components/rightsComponent.vue";
import confidencialComponent from "../components/confidencialComponent.vue";
import contactComponent from "../components/contactComponent.vue";



export default {
  components: {
    homeComponent,
    companyComponent,
    courierComponent,
    aboutComponent,
    rightsComponent,
    confidencialComponent,
    contactComponent
  },
  setup() {
    const activetabs = reactive({
      companyComponent: false,
      courierComponent: false,
      footerComponent: 'aboutComponent'
    });

    const handleCompany = () => {
      if (activetabs.courierComponent === true) {
        scroll(".lookingfor__components");
        activetabs.courierComponent = false;
        activetabs.companyComponent = !activetabs.companyComponent;
      } else if (activetabs.courierComponent === false &&  activetabs.companyComponent === false){
        scroll(".lookingfor__components");
        activetabs.companyComponent = !activetabs.companyComponent;
      } else{
        activetabs.companyComponent = !activetabs.companyComponent;
      }
    };

    const handleCourier = () => {
      if (activetabs.companyComponent === true) {
        scroll(".lookingfor__components");
        activetabs.companyComponent = false;
        activetabs.courierComponent = !activetabs.courierComponent;
      } else if( activetabs.companyComponent === false &&  activetabs.courierComponent === false){
        activetabs.courierComponent = !activetabs.courierComponent;
        scroll(".lookingfor__components");
      } else {
        activetabs.courierComponent = !activetabs.courierComponent;
      }
    };
    const scroll = (component) => {
      document.querySelector(component).scrollIntoView({
        behavior: "smooth",
      });
    };
    const rightsComponent = () =>{
      activetabs.footerComponent = 'rightsComponent';
      scroll('.footerComponent')
    }
    const confidencialComponent = () =>{
      activetabs.footerComponent = 'confidencialComponent'
      scroll('.footerComponent')
    }
    const contactComponent = () =>{
      activetabs.footerComponent = 'contactComponent'
      scroll('.footerComponent')
    }

    return {
      activetabs,
      handleCompany,
      handleCourier,
      scroll,
      rightsComponent,
      confidencialComponent,
      contactComponent
    };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/main.scss";

.for-all-components {
  width: 100%;
  min-height: 100vh;
  background-color: $orange;
}

// lookingfor component
.lookingfor {
  &__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    flex-direction: column;
    padding: 0 260px;
    width: 100%;
    height: 100%;

    .all-lookingfor-wrappers {
      margin: 35px 0;
    }
    &-header {
      width: 100%;
      &-img {
        background-image: url("../assets/img/Ellipse9.png");
        background-size: 400px 100%;
        background-position: center;
        background-repeat: no-repeat;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 20vh;
        vertical-align: middle;
        &-inner {
          width: 100%;
          height: 20vh;
          background-image: url("../assets/img/Group41.png");
          background-size: 250px;
          background-position: center;
          background-repeat: no-repeat;
        }
      }
    }
    &-title {
      width: 100%;
      height: 170px;
      display: flex;
      align-items: center;
      justify-content: center;

      h3 {
        line-height: 3.5rem;
        padding: 0px 10px;
        text-align: center;
      }
    }
    &-buttons {
      width: 100%;
      height: 120px;
      display: flex;
      align-items: center;
      justify-content: center;

      &-button {
        width: 50%;
        height: 100%;
        border: 1px solid $black;
        z-index: 1;
        position: relative;

        span {
          text-align: center;
          font-size: 32px;
          transition: color 300ms ease-in-out;
        }
        &::before {
          content: "";
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          z-index: -1;
          background-color: $black;
          transition: transform 300ms ease-in-out;
          transform: scaleX(0);
        }
        &:hover::before {
          transform: scaleX(1);
        }
        &:focus::before {
          transform: scaleY(1);
        }
        &:hover {
          span {
            color: $orange;
          }
        }
        &:focus {
          span {
            color: $orange;
          }
        }
      }
    }

  }
  &__hr{
    width: 80%;
    height: 1px;
    background-color: $black;
    margin: 0 auto;

  }
  .companyComponent {
    width: 100%;
    height: 100vh;
  }
  .fade-enter-from {
    height: 0;
    opacity: 0;
  }
  .fade-enter-to {
    height: 100vh;
    opacity: 1;
  }
  .fade-enter-active {
    transition: all .7s ease;
  }
  .fade-leave-from {
    height: 100vh;
    opacity: 1;
  }
  .fade-leave-to {
    opacity: 0;
    height: 0;
    padding: 0;
  }
  .fade-leave-active {
    transition: all .7s ease;
  }

}

// about component

.about {
  width: 100%;
  height: 100vh;
  padding-top: 35px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
  &__buttons{
    width: 100%;
    height: 15%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    &-btn{
      span{
        font-size: 24px;
      }
    }
  }
  .fadeUp-enter-from {
    height: 0;
    opacity: 0;
  }
  .fadeUp-enter-to {
    height: 100vh;
    opacity: 1;
  }
  .fadeUp-enter-active {
    transition: all .7s ease;
  }
  .fadeUp-leave-from {
    height: 100vh;
    opacity: 1;
  }
  .fadeUp-leave-to {
    opacity: 0;
    height: 0;
    padding: 0;
  }
  .fadeUp-leave-active {
    transition: all .7s ease;
  }
}
</style>
