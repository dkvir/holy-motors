<template>
  <div class="header">
    <div class="header__background">
      <div class="buttons">
        <button class="btn btn-company">კომპანიები</button>
        <button class="btn btn-rights">კურიერები</button>
      </div>
    </div>
  </div>
  <div class="home__body">

    <div class="home__body-title body-both">
      <img src="../assets/img/Group119.png" alt="title">
    </div>

    <div class="home__body-slogan body-both">
      <img src="../assets/img/Group85.png" alt="slogan">
    </div>

    <div class="home__body-right body-both">
      <video class="video" autoplay loop muted>
        <source src="../assets/video/MOT2video.mp4" type="video/mp4">
      </video>
      <div class="onvideo-animation"></div>
    </div>

    <div class="home__body-download body-both">
      <div class="home__body-download-wrapper">
        <button class="download-one"><a href="#"><img src="../assets/img/Component2.png" alt="download"></a></button>
        <button class="download-one"><a href="#"><img src="../assets/img/Component2.png" alt="download"></a></button>   
      </div>
        <div class="download-three"><a href="#"><img src="../assets/img/Group1.png" alt="download"></a></div>
    </div>

  </div>
  <div class="home__bottom"></div>


</template>

<script>

export default {

}
</script>

<style lang="scss">
@import '../assets/scss/main.scss';
@import '../assets/scss/fonts/fonts.scss';


.header{
  width: 100%;
  height: 80px;
  border-bottom: 1px solid black;
  &__background{
    background-image: url('../assets/img/headeranim.png');
    width: 100%;
    height: 80px;
    animation: moveBg 30s linear infinite;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    position: relative;
    .btn{
      width: 200px;
      height: 80px;
      background-color:$black;
      color:$orange;

    }
    .btn-company{
      clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
      position: absolute;
      top:0;
      right: 135px;
    }
    .btn-rights{
      clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
      position: absolute;
      top:0;
      right: -20px;
    }
  }

}

.home__body{
  width: 100%;
  height: 80vh;
  display: grid;
  grid-template-columns:60% 40%;
  grid-template-rows: 65% 15% 20%;
  padding: 60px 0px;
  .body-both{
    width: 100%;
    height: 100%;
  }
  &-title{
    grid-column-start: 1;
    grid-row-start: 1;
    padding: 40px 80px 20px 120px;
    img{
      width: 100%;
      height: 90%;
    }
  }
  &-slogan{
    grid-column-start: 1;
    grid-row-start: 2;
    padding-left: 120px;
    img{
      width: 50%;
      height: 70%;
    }
  }
  &-right{
    grid-column-start: 2;
    grid-row-start: 1;
    grid-row-end: 4;
    .video{
      height: 100%;
      border-radius: 30px 0px 0px 30px;
      border: 4px solid $black;
    }
    .onvideo-animation{
      position: relative;
      top: -100px;
      right: -155px;
      height: 50px;
      width: 70%;
      background-image: url('../assets/img/Group111.png');
      animation: moveBg 7s linear infinite;
    }
  }
  &-download{
    grid-column-start: 1;
    grid-row-start: 3;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
    height: 100%;
    padding: 0px 120px;
    &-wrapper{
      display: flex;
      align-items: center;
      justify-content: space-around;
      width: 100%;
      height: 70%;
    }
    .download-one{
      background-color: transparent;
      img{
      width: 98%;
      height: 100%;
      transition: .2s linear;
      border-radius: 40px;
      &:hover{
      background-color: white;
      }
    //   &::before{
    //     position: absolute;
    //     left: 0;
    //     top: 0;
    //     width: 98%;
    //     height: 100%;
    //     border-radius: 35px;
    //     background: #fff;
    //     z-index: -1;
    //     transition: transform 0.5s;
    //     transition-timing-function: cubic-bezier(0.5,1.6,0.4,0.7);
    //     transform-origin: 0 0;
    //     transform: scaleY(0);
    //   }
    //   &:hover::before{
    //     transform: scaleY(1);
    //   }
    }
  

    }
    .download-three{
      img{
      width: 65%;
      height: 100%;
      padding-left: 100px;
    }
    }
    
  }
  

}
.home__bottom{
    width: 90%;
    height: 50px;
    background-image:url('../assets/img/Group69.png');
    animation: moveBg 10s linear infinite;

    
  }

</style>