<template>
  <footer>
    <div class="footer-content github">
        Vind je een probleem op de pagina? Fix het op onze open-source <a target="_blank" href="https://github.com/rohitjethoe/codekamp">GitHub Repository.</a>
    </div>
    <div class="footer-content socials">
        <a target="_blank" href="">
            <i class="fa-brands fa-instagram"></i>
        </a>
        <a target="_blank" href="">
            <i class="fa-brands fa-tiktok"></i>
        </a>
        <a target="_blank" href="https://github.com/rohitjethoe/codekamp">
            <i class="fa-brands fa-github"></i>
        </a>
        <a target="_blank" href="">
            <i class="fa-brands fa-discord"></i>
        </a>
    </div>
    <div class="footer-content copyright">
        <a target="_blank" href="">
            Made with <span class="heart">❤</span> by Rohit
        </a>
    </div>
  </footer>
</template>

<script>
export default {
    name: "FooterComponent"
}
</script>

<style lang="scss" scoped>
    footer {
        background-color: #faedcd;
        padding-top: 24px;
        text-align: center;
        .footer-content {
            padding: 10px 5vw;
        }
        .github {
            a:link, a:visited {
                color: #282828;
                font-weight: 600;
                text-decoration: none;
            }
        }
        .socials {
            a:link, a:visited {
                color: #282828;
                font-size: 20px;
                margin: 0px 8px;
            }
        }
        .copyright {
            a:link, a:visited {
                color: #282828;
                text-decoration: none;
                .heart {
                    color: #db0000;
                }
            }
        }
    }
</style>