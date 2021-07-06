<template>
  <div class="company">
    <div class="company__header">
      <div class="company__header-title"><h3>MOT2 - პარტნიორის აპლიკაცია</h3></div>
      <div class="company__header-slogan"><h4>MOT2 – საკვების, პროდუქტებისა და ამანათების მიტანის ქართული კომპანია.</h4></div>
      <div class="company__header-img"><img src="../assets/img/Group205.png" alt="confidencial"></div>
    </div>
    <form @submit.prevent="" class="company__form">
      <div class="company__form-inputs">
        <input type="text" placeholder="კომპანიის დასახელება">
        <input type="text" placeholder="კომპანიის დასახელება">
        <input type="text" placeholder="კომპანიის დასახელება">
        <input type="text" placeholder="კომპანიის დასახელება">
      </div>
      <div class="company__form__checkbox">
        <div class="company__form__checkbox-title"><p>ამჟამად რომელი საკურიერო კომპანიებთან თანამშრომლობთ?</p></div>
        <div class="company__form__checkbox__boxes">
          <div class="company__form__checkbox__boxes-box">
            <input type="checkbox" id="company1" name="company1" value="company1">
            <label for="company1">გლოვო</label>
          </div>
          <div class="company__form__checkbox__boxes-box">
            <input type="checkbox" id="company 2" name="company 2" value="company2">
            <label for="company 2">ვოლტი</label>
          </div>
          <div class="company__form__checkbox__boxes-box">
            <input type="checkbox" id="company 3" name="company 3" value="company3">
            <label for="company 3">ელვისი</label>
          </div>
          <div class="company__form__checkbox__boxes-box">
            <input type="checkbox" id="company 4" name="company 4" value="company4">
            <label for="company 4">ბოლტი</label>
          </div>
          <div class="company__form__checkbox__boxes-box">
            <input type="checkbox" id="company 5" name="company 5" value="company5">
            <label for="company 5">სხვა</label>
          </div>
          
        </div>
      </div>
      <div class="company__form-coment">
        <input type="text" placeholder="კომენტარი ორი სიტყვით">
      </div>
      <div class="company__form-button">
        <button>გაგზავნა</button>
      </div>
    </form>
    
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import '../assets/scss/main.scss';
@import '../assets/scss/fonts/fonts.scss';
.company{
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
  flex-wrap: wrap;
  padding: 50px 260px;
  &__header{
    width: 100%;
    height: 30%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
    text-align: center;
    img{
      width: 70%;
      padding-top: 20px;
    }
  }
  .company__form{
    width: 100%;
    height: 70%;
    display: flex;
    align-items: center;
    justify-content: space-around;
    flex-direction: column;
    flex-wrap: wrap;
    padding-top: 20px;

    &-inputs{
      width: 100%;
      display: grid;
      grid-template-rows: auto auto;
      grid-template-columns: auto auto;
    }
    &__checkbox{
      width: 100%;
      height: 30%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-direction: column;
      flex-wrap: wrap;
      &-title{
        height: 50%;
        width: 100%;
        text-align: center;
      }
      &__boxes{
        width: 100%;
        height: 50%;
        display: flex;
        align-items: center;
        justify-content: space-between;

        &-box{
          width: 25%;
          height: 100%;
          display: flex;
          align-items: center;
          justify-content: space-around;
          padding: 0 20px;

        }
      }
    }
    &-coment{
      width: 100%;
    }
    &-button{
      width: 100%;
      height: 10%;
      button{
        width: 100%;
        height: 100%;
        background-color: black;
        color: $orange;
      }
    }
  }
}
</style>