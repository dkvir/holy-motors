<template>
  <section class="home for-all-components">
    <homeComponent
      :scroll="scroll"
      :handleCourier="handleCourier"
      :handleCompany="handleCompany"
      :activetabs="activetabs"
      :rightsComponent="rightsComponent"
      :confidencialComponent="confidencialComponent"
      :contactComponent="contactComponent"
      :aboutComponent="aboutComponent"
    />
  </section>
  <section class="lookingfor for-all-components">
    <div class="lookingfor__wrapper">
      <div class="lookingfor__wrapper-header all-lookingfor-wrappers">
        <div class="lookingfor__wrapper-header-img">
          <div class="lookingfor__wrapper-header-img-inner"></div>
        </div>
      </div>
      <div class="lookingfor__wrapper-title all-lookingfor-wrappers">
        <h2>
          პარტნიორ კომპანიებსა და კურიერებს, რომლებიც ჩვენთან ერთად
          დაამკვიდრებენ სერვისის შეუდარებელ სტანდარტს.
        </h2>
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
  </section>
  <section class="about for-all-components">
    <transition name="fadeUp"> 
        <component class="footerComponent" :is="activetabs.footerComponent" />
    </transition>  
    <div class="about__buttons ">
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
  </section>
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
    const aboutComponent = () =>{
      activetabs.footerComponent = 'aboutComponent'
      scroll('.about')
    }
   

    return {
      activetabs,
      handleCompany,
      handleCourier,
      scroll,
      rightsComponent,
      confidencialComponent,
      contactComponent,
      aboutComponent,
      
    };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/main.scss";
@import "../assets/scss/responsive.scss";

.for-all-components {
  max-width: 100%;
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
    padding: 5vh 260px;
    width: 100%;
    height: 100%;


    &-header {
      width: 100%;
      height: 20vh;
      &-img {
        background-image: url("../assets/img/Ellipse9.png");
        background-size: auto 100%;
        background-position: center;
        background-repeat: no-repeat;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        vertical-align: middle;
        &-inner {
          width: 80%;
          height: 80%;
          background-image: url("../assets/img/Group41.png");
          background-size: 50% auto;
          background-position: center;
          background-repeat: no-repeat;
        }
      }
    }
    &-title {
      width: 100%;
      height: 55vh;
      display: flex;
      align-items: center;
      justify-content: center;

      h2 {
        padding: 0px 10px;
        text-align: center;
      }
    }
    &-buttons {
      width: 100%;
      height: 15vh;
      display: flex;
      align-items: center;
      justify-content: center;

      &-button {
        width: 50%;
        height: 100%;
        border: 3px solid $black;
        margin-bottom: 10px;
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
  height: 85vh;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
  &__buttons{
      width: 100%;
      height: 15vh;
      display: flex;
      align-items: center;
      justify-content: space-between;
      background-color: $orange;
      &-btn{
        span{
          font-size: 24px;
        }
      }
    }

}

  .fadeUp-enter-from {
    height: 0;
    opacity: 0;
  }
  .fadeUp-enter-to {
    height: 85%;
    opacity: 1;
  }
  .fadeUp-enter-active {
    transition: all .7s ease;
  }
  .fadeUp-leave-from {
    height: 85%;
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
</style>
