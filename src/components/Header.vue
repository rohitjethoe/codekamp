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
    <div 
    :class="navOpened ? 'map-opened' : ''"
    class="map">
        <div class="map-header">
            <div class="logo">
                codekamp.
            </div>
            <div class="nav" @click="$event => openNav()">
                <div class="exitLine line-1"></div>
                <div class="exitLine line-2"></div>
            </div>
        </div>
        <div class="map-menu">
            <div class="menu">
                <div class="title">
                    Menu
                </div>
                <ul>
                    <li>
                        <a href="/">Home</a>
                    </li>
                    <li>
                        <a href="/leren">Leren</a>
                    </li>
                    <li>
                        <a href="/projecten">Projecten</a>
                    </li>
                    <li>
                        <a href="/gids">Gidsen</a>
                    </li>
                    <li>
                        <a href="/about">Over Ons</a>
                    </li>
                </ul>
            </div>
            <div class="menu">
                <div class="title">
                    Laatste artikelen
                </div>
                <div class="articles">
                    <div 
                    v-for="article in articles.slice(0, 2)" 
                    v-bind:key="article"
                    class="article">
                        <a 
                        :href="article.canonical_url"
                        target="_blank">
                            <div class="article-url">
                                {{ article.title }}
                            </div>
                            <div class="article-writer">
                                {{ article.user.name }} | {{ new Date(article.published_at).getDate() }} {{ months[new Date(article.published_at).getMonth()] }} {{ new Date(article.published_at).getFullYear() }}
                            </div>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            navOpened: false,
            months: ['Januari', 'Februari', 'Maart', 'April', 'Mei', 'Juni', 'Juli', 'Augustus', 'September', 'Oktober', 'November', 'December', ]
        }
    },
    methods: {
        openNav: function () {
            this.navOpened = !this.navOpened;
        }
    },
    props: {
        articles: JSON
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
                    width: 30px;
                }
            }
            .burger-icon-opened {
                .bar:nth-child(2) {
                    width: 30px;
                }
            }
        }
        .map {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: #282828;
            .map-header {
                display: flex;
                align-items: center;
                justify-content: space-between;
                .logo {
                    color: #fff;
                }
                .nav {
                    .exitLine {
                        width: 24px;
                        height: 3px;
                        background-color: #fff;
                        border-radius: 3px;
                    }
                    .line-1 {
                        transform: translate(-2px, 1px) rotate(45deg);
                    }
                    .line-2 {
                        transform: translate(-2px, -2px) rotate(-45deg);
                    }
                }
            }
            .map-menu {
                color: #FFF;
                .menu {
                    .title {
                        color: #c5c5c5;
                        border-bottom: 3px solid #c5c5c5;
                        text-transform: uppercase;
                        font-weight: 600;
                    }
                    ul {
                        li {
                            list-style-type: none;
                            a:link, a:visited {
                                color: #fff;
                                text-decoration: none;
                            }
                        }
                    }
                    .articles {
                        .article {
                            a:link, a:visited {
                                color: #fff;
                                text-decoration: none;
                            }
                            .article-writer {
                                color: #c5c5c5;
                            }
                        }
                    }
                }
            }
        }
        .map-opened {
            display: block;
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
            .map {
                .map-header {
                    .nav {
                        padding: 10px 12px;
                    }
                    .nav:hover {
                        cursor: pointer;
                    }
                }
                .map-menu {
                    width: 80vw;
                    margin: 20px 30px;
                    .menu {
                        .title {
                            padding: 20px 0px;
                        }
                        ul {
                            margin: 20px 0px;
                            li {
                                font-size: 30px; 
                                margin: 16px 0px;
                            }
                        }
                        .articles {
                            padding: 20px 0px;
                            .article {
                                padding-bottom: 20px;
                                .article-url {
                                    
                                }
                            }
                        }
                    }
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
            .map {
                .map-header {
                    .nav {
                        padding: 15px 20px;
                    }
                }
                .map-menu {
                    width: 50vw;
                    margin: 20px 30px;
                    .menu {
                        .title {
                            padding: 20px 0px;
                        }
                        ul {
                            margin: 20px 0px;
                            li {
                                font-size: 30px; 
                                margin: 16px 0px;
                            }
                        }
                        .articles {
                            padding: 20px 0px;
                            .article {
                                padding-bottom: 20px;
                                .article-url {
                                    
                                }
                            }
                        }
                    }
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
            .map {
                .map-header {
                    .nav {
                        padding: 15px 20px;
                    }
                }
                .map-menu {
                    margin: 50px auto;
                    display: flex;
                    gap: 60px;
                    width: 80vw;
                    .menu {
                        width: 360px;
                        .title {
                            padding: 20px 0px;
                        }
                        ul {
                            margin: 20px 0px;
                            li {
                                font-size: 30px; 
                                margin: 16px 0px;
                            }
                        }
                        .articles {
                            padding: 20px 0px;
                            .article {
                                padding-bottom: 20px;
                                .article-writer {
                                    margin: 4px 0px;
                                }
                            }
                        }
                    }
                }
            }
        }
    }
</style>