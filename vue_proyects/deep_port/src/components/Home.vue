<template>
  <div class="Home">
    <!-- <article class="hero bg-img" :style="{ backgroundImage: `url('${capa1}')` }"> -->
    <article class="hero bg-img">
      <section class="layer one bg-img w-100 h-100"></section>
      <section class="layer two bg-img w-100 h-100"></section>
      <section
        class="content container-fluid h-100 d-flex justify-content-center align-items-center"
      >
        <div class="landscape w-100 h-100">
          <div class="night-fall">
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
            <div class="shooting_star"></div>
          </div>
        </div>
      </section>
    </article>
    <article class="animation d-flex justify-content-center align-items-center">
      <section
        class="animation-zone h-100 w-100 d-flex align-items-center justify-content-center position-relative"
      >
        <img
          src="../assets/img/sun.png"
          class="animation-img bg-sun img-fluid h-100 position-absolute"
          alt
        >
        <img
          src="../assets/img/fondo.png"
          class="animation-img bg-landscape img-fluid h-100 position-absolute"
          alt
        >
        <img
          src="../assets/img/alice.png"
          class="animation-img bg-character img-fluid h-100 position-absolute"
          alt
        >
        <!-- <h2 class="text-center">animation</h2> -->
      </section>
      <div class="night">
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
      </div>
    </article>
  </div>
</template>
<script>
// vue-owl-carousel solo nse puede usar en el componente donde se va a declarar el template
import carousel from "vue-owl-carousel";
export default {
  name: "Home",
  data() {
    return {
      msg: "Hello there",
      capa1: "/assets/img/portafolio_capa1.png"
    };
  },
  components: { carousel },
  methods: {
    changed() {
      // console.log('hey listen');
    }
  }
};
</script>

<style lang="scss">
@import "src/global";
.typed-cursor {
  font-size: 2.5rem;
}
.hero {
  height: calc(100vh - 50px);
  position: relative;
  .layer {
    background-repeat: repeat;
    background-position: 0 0;
    position: absolute;
    top: 0;
    &.one {
      animation: cloudAn 350s linear infinite;
      background-image: url("../assets/img/portafolio_capa1.png");
    }
    &.two {
      background-image: url("../assets/img/portafolio_capa2.png");
      animation: cloudAn 250s reverse infinite;
    }
  }
  .content-hero {
    color: $secundario;
  }
  @keyframes cloudAn {
    from {
      background-position: 0 0;
    }
    to {
      background-position: -5000px 0;
    }
  }
}
.animation {
  height: 45vh;
  //background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
  position: relative;
  overflow: hidden;
  .animation-img {
    overflow: hidden;
    &.bg-sun {
      animation: sunMove 10s linear 0s infinite reverse;
      // animation-play-state: paused;
    }
    &.bg-landscape {
    }
    &.bg-character {
      transition: all 0.5s ease;
      animation: float 1s linear 0s infinite alternate;
      &:hover {
        // background-color: #bada55;
      }
    }
    @keyframes sunMove {
      0% {
        // transform: translate(0%, 0%);
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
        // transform: translate(100%, 0%);
      }
    }
    @keyframes float {
      from {
        transform: translate(0, 0);
      }

      to {
        transform: translate(0, 2%);
      }
    }
  }
  @include responsive(tablet) {
    // background-color: #bada55;
  }
}
.night {
  position: absolute;
  width: 100%;
  height: 100%;
  transform: rotateZ(135deg);
  // animation: sky 200000ms linear infinite;
  $shooting-time: 3000ms;
  .shooting_star {
    position: absolute;
    left: 50%;
    top: 50%;
    // width: 100px;
    height: 2px;
    background: linear-gradient(
      -45deg,
      black,
      rgba(0, 0, 255, 0)
    ); //color de las estrella?
    border-radius: 999px;
    filter: drop-shadow(0 0 6px rgba(0, 0, 0, 0.541));
    animation: tail $shooting-time ease-in-out infinite,
      shooting $shooting-time ease-in-out infinite;
    // &::before {
    //     content: '';
    //     position: absolute;
    //     top: calc(50% - 1px);
    //     right: 0;
    //     // width: 30px;
    //     height: 2px;
    //     background: linear-gradient(-45deg, rgba(0, 0, 255, 0), rgba(95, 145, 255, 1), rgba(0, 0, 255, 0));
    //     transform: translateX(50%) rotateZ(45deg);
    //     border-radius: 100%;
    //     animation: shining $shooting-time ease-in-out infinite;
    // }
    // &::after {
    //     @extend .shooting_star::before;
    //     transform: translateX(50%) rotateZ(-45deg);
    // }
    @for $i from 1 through 20 {
      &:nth-child(#{$i}) {
        $delay: random(9999) + 0ms;
        top: calc(50% - #{random(400) - 200px});
        left: calc(50% - #{random(300) + 0px});
        animation-delay: $delay;
        // opacity: random(50) / 100 + 0.5;

        &::before,
        &::after {
          animation-delay: $delay;
        }
      }
    }
  }
  @keyframes tail {
    0% {
      width: 0;
    }

    30% {
      width: 100px;
    }

    100% {
      width: 0;
    }
  }

  @keyframes shining {
    0% {
      width: 0;
    }

    50% {
      width: 30px;
    }

    100% {
      width: 0;
    }
  }

  @keyframes shooting {
    0% {
      transform: translateX(0);
    }

    100% {
      transform: translateX(300px);
    }
  }

  @keyframes sky {
    0% {
      transform: rotate(45deg);
    }

    100% {
      transform: rotate(45 + 360deg);
    }
  }
}
.portfolio {
  $height_porfolio: 75vh;
  $mt_porfolio: 2vh;
  .item {
    height: ($height_porfolio / 2) - $mt_porfolio;
    margin-top: $mt_porfolio;
  }
}
.landscape {
  overflow: hidden;
  .night-fall {
    height: 100%;
    width: 100%;
    transform: rotateZ(135deg);
    $shooting-time: 3000ms;
    .shooting_star {
      position: absolute;
      left: 50%;
      top: 50%;
      // width: 100px;
      height: 2px;
      background: linear-gradient(
        -45deg,
        black,
        rgba(0, 0, 255, 0)
      ); //color de las estrella?
      border-radius: 999px;
      filter: drop-shadow(0 0 6px rgba(0, 0, 0, 0.541));
      animation: tail $shooting-time ease-in-out infinite,
        shooting $shooting-time ease-in-out infinite;

      // &::before {
      //     content: '';
      //     position: absolute;
      //     top: calc(50% - 1px);
      //     right: 0;
      //     // width: 30px;
      //     height: 2px;
      //     background: linear-gradient(-45deg, rgba(0, 0, 255, 0), rgba(95, 145, 255, 1), rgba(0, 0, 255, 0));
      //     transform: translateX(50%) rotateZ(45deg);
      //     border-radius: 100%;
      //     animation: shining $shooting-time ease-in-out infinite;
      // }
      // &::after {
      //     @extend .shooting_star::before;
      //     transform: translateX(50%) rotateZ(-45deg);
      // }
      @for $i from 1 through 20 {
        &:nth-child(#{$i}) {
          $delay: random(9999) + 0ms;
          top: calc(50% - #{random(400) - 200px});
          left: calc(50% - #{random(300) + 0px});
          animation-delay: $delay;
          // opacity: random(50) / 100 + 0.5;

          &::before,
          &::after {
            animation-delay: $delay;
          }
        }
      }
    }
    @keyframes tail {
      0% {
        width: 0;
      }

      30% {
        width: 100px;
      }

      100% {
        width: 0;
      }
    }

    @keyframes shining {
      0% {
        width: 0;
      }

      50% {
        width: 30px;
      }

      100% {
        width: 0;
      }
    }

    @keyframes shooting {
      0% {
        transform: translateX(0);
      }

      100% {
        transform: translateX(300px);
      }
    }

    @keyframes sky {
      0% {
        transform: rotate(45deg);
      }

      100% {
        transform: rotate(45 + 360deg);
      }
    }
  }
}
</style>
