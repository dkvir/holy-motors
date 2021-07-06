<template>
  <div class="footers">
    <div class="home__bottom footers__hAnim"></div>
    <div class="footers__body">
      <div class="footers__body-bAnim"></div>
      <div class="footers__body__wrapper">
        <div class="rights">
          <div class="rights__title">
            <div class="rights__title-icon">
              <fa class="icon" :icon="['fas', 'arrow-right']" />
            </div>
            <div class="rights__title-text">
              <h4>მომხმარებელთა მომსახურების პირობები</h4>
            </div>
          </div>
          <div class="rights__body">
            <p>„MOT2-ის მომსახურებით“ სარგებლობით, თქვენ თანხმობას აცხადებთ, რომ
            თქვენზე გავრცელდეს ეს მომხმარებელთა მომსახურების პირობები
            („მომსახურების პირობები“).</p>
            <p>გთხოვთ, „MOT2-ის მომსახურებით“
            სარგებლობამდე ყურადღებით წაიკითხოთ წინამდებარე „მომსახურების
            პირობები“. თუ თქვენ არ ეთანხმებით „მომსახურების პირობებს“, გთხოვთ,
            არ ისარგებლოთ „MOT2-ის მომსახურებით“. ეს „მომსახურების პირობები“
            ვრცელდება „MOT2-ის მომსახურებით“ ნებისმიერი ფორმით სარგებლობაზე და
            წინამდებარე დოკუმენტის საფუძველზე გაფორმებულ „ნასყიდობის
            ხელშეკრულებებზე“. „Wolt-ის მომსახურების“ უფრო დეტალური აღწერილობა და
            სისტემის მოთხოვნების შესახებ ინფორმაცია ხელმისაწვდომია ვებ-გვერდზე
            MOT2.com.</p>
            <p>თუ თქვენ გაქვთ „ანგარიში - MOT2-ი სამსახურში“, ეს
            „მომსახურების პირობები“ აგრეთვე ვრცელდება ჩვენს კლიენტ
            ორგანიზაციაზე, რომელიც საშუალებას გაძლევთ გამოიყენოთ „ფუნქცია -
            MOT2-ი სამსახურში“ („კლიენტი ორგანიზაცია“) იმ შეკვეთებთან
            დაკავშირებით, რომლებსაც თქვენ განახორციელებთ „ფუნქცია - MOT2-ი
            სამსახურში“-ს საშუალებით. ამ „მომსახურების პირობებსა“ და „MOT2-ის
            კორპორატიულ პირობებს“ შორის, რომელიც ვრცელდება „კლიენტ
            ორგანიზაციაზე“, შეუსაბამობის არსებობის შემთხვევაში უპირატესობა
            ენიჭება „MOT2-ის კორპორატიულ პირობებს“.</p>
            <p>„მომსახურების პირობები“
            ფორმდება მხოლოდ ჩვენსა და „მომხმარებელს“ შორის, და არა „ეფლ ინკ.“
            (Apple Inc.)-თან და „ეფლ ინკ.“ (Apple Inc.) არ არის პასუხისმგებელი
            „MOT2-ის აპლიკაციაზე“ ან მის შინაარსზე. თქვენ აცხადებთ თანხმობას,
            რომ „ეფლ ინკ.“ (Apple Inc.) და „ეფლ ინკ.“ (Apple Inc.)-ის შვილობილი
            კომპანიები („ეფლი“), „მომსახურების პირობებისთვის“ წარმოადგენენ
            მესამე პირებს, რომელთა სასარგებლოდაც დაიდო ხელშეკრულება და
            „მომსახურების პირობებზე“ თქვენი თანხმობის საფუძველზე „ეფლს“ ექნება
            უფლება (და იგულისხმება, რომ გაცხადებულია თანხმობა ასეთ უფლებაზე),
            რომ გამოიყენოს „მომსახურების პირობები“ თქვენ წინააღმდეგ, როგორც
            მესამე პირმა, რომლის სასარგებლოდაც დაიდო ხელშეკრულება.</p>
              
          </div>
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
  background-color: cornsilk;
  position: relative;
  &__hAnim {
    width: 100%;
    height: 50px;
    background-repeat: no-repeat;
    position: absolute;
    top: -25px;
  }
  &__body {
    width: 100%;
    height: 100%;
    background-color: $black;
    display: flex;
    padding: 30px;
    color: $orange;
    overflow: scroll;
    &-bAnim {
      background-image: url("../assets/img/Group224.png");
      background-repeat: no-repeat;
      background-position: center;
      animation: moveBg 7s linear infinite;
      width: 20px;
      height: 80%;
      background-repeat: no-repeat;
      margin-top: 60px;
      margin-right: 60px;
    }
    &__wrapper {
      width: 100%;
      height: 100%;

      .rights {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: flex-start;
        justify-content: space-between;
        flex-direction: column;
        &__title {
          width: 100%;
          height: 10%;

          display: flex;
          align-items: center;
          &-icon {
            width: 25px;
            height: 25px;
            background-color: $orange;
            color: $black;
            border-radius: 50%;
            margin-right: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
          }
          &-text {
            color: #fff;
          }
        }
        &__body{
            width: 100%;
            height: 90%;
            overflow: scroll;
            p{
            font-family: "Helvetica_normal";
            padding: 10px;
            line-height: 1.5rem;
            }
        }
      }

    }
  }

}
</style>
