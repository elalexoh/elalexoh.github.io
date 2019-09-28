<template>
<header class="main-menu bg-pattern">
  <div class="container-fluid h-100">
    <nav class="nav justify-content-between">
      <a class="nav-link active brand-logo" href="#">
        <p class="brand-text">Deeply</p>
      </a>
      <div>
        <b-button v-b-modal.modal-1 class="position-relative">Resume</b-button>

        <b-modal id="modal-1" centered size="xl" title="" :body-text-variant="bodyTextVariant">
          <p class="my-4">Hello from modal!</p>
        </b-modal>
      </div>
    </nav>
  </div>
</header>
</template>

<style lang="scss">
@import 'src/global';
  header {
    position: relative;
    z-index: 100;
  }
  .main-menu {
    background-color: $primario;
    // background-color: map-get($colors, primario );
    // background-image: url('../assets/img/pattern_positive.png');
    // background-blend-mode: multiply;
    height: 50px;
    .nav {
      height: 50%;
      font-family: $stylish_reg;
      display: flex;
      align-items: center;
      .nav-link {
        color: $white;
        letter-spacing: .1em;
      }
    }
  }
</style>
