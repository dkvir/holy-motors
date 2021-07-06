<template>
  <div class="footers">
    <div class="home__bottom footers__hAnim"></div>
    <div class="footers__body">
      <div class="contact">
        <div class="contact__items">
          <div class="contact__items__icon">
            <fa class="icon" :icon="['fas', 'phone']" />

          </div>
          <div class="contact__items__title">
              <p>+ 995 32 2 25 54 52</p>
          </div>
        </div>
        <div class="contact__items">
          <div class="contact__items__icon">
            <fa class="icon" :icon="['fas', 'envelope']" />



          </div>
          <div class="contact__items__title"><p>mot2@info.ge</p></div>
        </div>
        <div class="contact__items">
          <div class="contact__items__icon">
            <fa class="icon" :icon="['fab', 'facebook']" />

          </div>
          <div class="contact__items__title"><p>MOT2</p></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "../assets/scss/main.scss";
@import "../assets/scss/fonts/fonts.scss";

.footers {
  width: 100%;
  height: 100%;
  position: relative;
  &__body {
    width: 100%;
    height: 100%;
    background-color: $black;
    display: flex;
    .contact{
        display: flex;
        align-items: center;
        justify-content: space-around;
        padding: 50px;
        color: $orange;
        width: 100%;
        height: 100%;
        &__items{
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;

            &__icon{
                width: 50%;
                height: 50%;
                background-color: $orange;
                border-radius: 50%;
                display: flex;
                align-items: center;
                justify-content: center;
                
                .icon{
                    width: 50%;
                    height: 50%;
                    color: $black;
                }
            }
            &__title{
                margin-top: 20px;
                width: 50%;
                height: 40px;
                background-color: $orange;
                color: $black;
                display: flex;
                align-items: center;
                justify-content: center;
            }
        }

    }
  }
}
</style>
