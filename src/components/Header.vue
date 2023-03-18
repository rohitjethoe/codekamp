<template>
  <header>
    <div class="logo">
        <a href="/">
            codekamp.
        </a>
    </div>
    <div class="nav">
        <div 
            @click="$event => openNav()"
            :class="navOpened ? 'burger-icon-opened' : ''" 
            class="burger-icon">
            <div class="bar bar-1"></div>
            <div class="bar bar-2"></div>
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            navOpened: true
        }
    },
    methods: {
        openNav: function () {
            this.navOpened = !this.navOpened;
        }
    }
}
</script>

<style scoped lang="scss">
    header {
        font-family: 'Sarabun', sans-serif;
        background-color: #DFE2CF;
        .logo {
            a:link, a:visited {
                color: #282828;
                text-decoration: none;
            }
        }
        .nav {
            .burger-icon {
                display: inline-block;
                cursor: pointer;
                .bar {
                    width: 30px;
                    height: 2px;
                    margin: 5px 0;
                    background-color: #282828;
                    transition: 0.5s all;
                }
                .bar:nth-child(2) {
                    width: 20px;
                }
            }
            .burger-icon-opened {
                .bar:nth-child(2) {
                    width: 30px;
                }
            }
        }
    }

    @media only screen and (max-width: 600px) {
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            .logo {
                padding: 10px 12px;
            }
            .nav {
                .burger-icon {
                    padding: 10px 12px;
                }
            }
        }
    }

    @media only screen and (min-width: 600px) and (max-width: 800px) {
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            .logo {
                padding: 15px 20px;
                font-size: 20px;
            }
            .nav {
                .burger-icon {
                    padding: 15px 20px;
                }
            }
        }
    }

    @media only screen and (min-width: 800px) {
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            .logo {
                padding: 20px 20px;
                font-size: 20px;
            }
            .nav {
                .burger-icon {
                    padding: 15px 20px;
                }
            }
        }
    }
</style>