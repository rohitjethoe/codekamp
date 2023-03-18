<template>
    <div class="info">
        <div class="heading">
            <h2>
                Waar moet ik beginnen?
            </h2>
        </div>
        <div class="content">
            <p><span>Programmeren</span> is een breed begrip. Vandaag wordt computercode schrijven toegepast op elk aspect in onze maatschappij.</p> 
            <br />
            <p>Denk aan website, desktop en mobile development. Maar ook Database, DevOps en Security Engineering. Daarnaast heb je nog Backend applicaties die worden gemaakt met AI, Automatisering en nog veel meer.</p> 
            <br>
            <p>Zoveel keus, maar <span>waar moet jij beginnen?</span></p>
            <br>
        </div>
        <div class="app">
            <div v-if="!startScanner" class="begin">
                <div class="question">
                    Doe onze test om je keuze te versimpelen.
                </div>
                <div
                    @click="$event => runScanner()" 
                    class="button">
                    Beginnen
                </div>
            </div>
            <Scanner v-else/>
        </div>
        <br>
    </div>
</template>

<script>
import Scanner from './apps/Scanner.vue';

export default {
    name: 'InfoComponent',
    data() {
        return {
            startScanner: false
        }
    },
    methods: {
        runScanner: function () {
            this.startScanner = !this.startScanner;
        }
    },
    components: {
        Scanner
    }
}
</script>

<style lang="scss" scoped>
    .info {
        background-color: #282828;
        color: #fff;
        .heading {
            h2 {
                background-color: #ccd5ae;
                display: inline-block;
            }
        }
        .content {
            color: #697780;
            p {
                span {
                    color: #fff;
                }
            }
        }
        .app {
            background-color: #b7c296;
            .begin {
                .question {
                    font-weight: 600;
                }
                .button {
                    background-color: #d4a373;
                    display: inline-block;
                    text-transform: uppercase;
                    font-weight: 600;
                    user-select: none;
                    -webkit-user-select: none;
                }
                .button:hover {
                    cursor: pointer;
                }
            }
        }
    }

    @media only screen and (max-width: 600px) {
        .info {
            padding: 80px 5vw;
            .heading {
                h2 {
                    padding: 10px 12px;
                    font-size: 20px;
                    margin: 20px 0px;
                }
            }
            .app {
                color: #282828;
                padding: 20px 0px;
                .begin {
                    width: 90%;
                    margin: 0px auto;
                    .button {
                        margin: 10px 0px;
                        padding: 10px 12px;
                    }
                }
            }
        }
    }
</style>