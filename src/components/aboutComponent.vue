<template>
  <div class="about__wrapper">
    <div class="about__wrapper-title allcols">
      <img src="../assets/img/whoweare.png" alt="" />
    </div>
    <div class="about__wrapper-topanim allcols">
        <!-- <div class="home__bottom"></div> -->
    </div>
    <div class="about__wrapper-bottanim allcols">
        <!-- <div class="home__bottom"></div> -->
    </div>
    <div class="about__wrapper-text allcols">
        <p>მრავალი წელია, თქვენს ასეულ ათასობით ამანათს კონტინენტებისა და ოკეანეების
      გავლით უსაფრთხოდ დავატარებთ. 26 მაისიდან გამოწერილ ამანათებს პირდაპირ
      სახლებსა და ოფისებში მოგიტანთ. ძალიან მალე ყოველდღიურ საყიდლებსაც და
      თბილისის საუკეთესო რესტორნების კერძებსაც!</p>
        <p>მოტ2 ახალი ქართული მიტანის
      სერვისია USA2GEORGIAს გუნდისგან. ჩვენი მთავარი მიზანია, თანამედროვე
      ტექნოლოგიების გამოყენებით გაგიმარტივოთ ცხოვრება.</p>
        <p>დიდი მადლობა ნდობისთვის!
      აპლიკაცია სატესტო რეჟიმში მუშაობს, ამიტომ თქვენი მხარდაჭერა ფასდაუდებელია
      ახალი ინიციატივის წარმატებისთვის.</p>
        
    </div>
    <div class="about__wrapper__logos allcols">
      <div class="about__wrapper__logos-img">
        <img src="../assets/img/Group6.png" alt="" />
      </div>
      <div class="about__wrapper__logos-img">
        <img src="../assets/img/Group46.png" alt="" />
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
.allcols {
  // overflow: hidden;
  justify-self: start;
}
.about__wrapper {
  height: 85%;
  width: 100%;
  display: grid;
  grid-template-columns: repeat(5, 20%);
  grid-template-rows: repeat(5, 20%);
  padding: 70px 0;

  &-title {
    grid-column-start: 2;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 3;
    width: 100%;

    img {
        width: 100%;
        height: 100%;

    }
  }
  &-topanim {
    width: 100%;
    height: 85%;
    margin-left: 120px;
    grid-column-start: 4;
    grid-column-end: 6;
    grid-row-start: 1;
    grid-row-end: 2;
    background-image: url('../assets/img/Group69.png');
    background-repeat: no-repeat;
    animation: moveBg 10s linear infinite;
    background-size: auto 100%;

  }
  &-bottanim {
    width: 100%;
    height: 85%;
    margin-right: 77px;
    margin-top: 123px;
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 3;
    grid-row-end: 4;
    background-image: url('../assets/img/Group69.png');
    background-repeat: no-repeat;
    background-size: auto 100%;
    animation: moveBg 10s linear infinite;


  }
  &-text {
    grid-column-start: 3;
    grid-column-end: 5;
    grid-row-start: 2;
    grid-row-end: 5;
    height: 100%;
    overflow: scroll;
    padding: 30px 30px;
    p{
      font-size: 24px;
      font-family: $Helvetica_normal;
      padding-bottom: 10px;
      line-height: 2.5rem;
    }
  }
  &__logos {
    grid-column-start: 3;
    grid-column-end: 5;
    grid-row-start: 5;
    grid-row-end: 6;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    flex-direction: column;
    flex-wrap: wrap;
    height: 100%;
    padding: 30px;
    img {
      width: 50%;
    }
  }
}
</style>
