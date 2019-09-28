<template>
    <footer class="footer-menu">
        <div class="container h-100">
            <nav class="nav justify-content-between h-50 align-items-center">
                <a class="nav-link active brand-logo" href="#">
                    <p class="brand-text">Deeply</p>
                </a>
                <div class="about-me w-50 text-right">
                    <h2>Hey!</h2>
                    <p class="w-75 ml-auto">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta veniam ipsum alias libero necessitatibus, ad odio laudantium saepe omnis iure reiciendis eos aliquid, magni
                    </p>
                </div>
            </nav>
            <div class="social-media w-100 h-50 d-flex align-items-center">
                <ul class="d-flex list-unstyled w-100 justify-content-around">
                    <li>
                        <a href="#" class="link">red</a>
                    </li>
                    <li>
                        <a href="#" class="link">red</a>
                    </li>
                    <li>
                        <a href="#" class="link">red</a>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>
<style lang="scss">
  @import "../styles/partials/_colors.scss";
  @import "../styles/partials/_fonts.scss";
    .footer-menu {
        height: 55vh;
        background-color: $primario;
        .brand-logo,
        .link {
            color: $white;
        }
        .about-me {
            color: $white;
        }
    }
</style>
