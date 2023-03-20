<template>
  <div class="scanner">
    <div v-if="current < (Object.keys(this.questions).length)" class="question">
        <a @click="$event => setAnswer(0)">
            {{ questions[current].answers[0] }}
        </a> 
        of
        <a @click="$event => setAnswer(1)">
            {{ questions[current].answers[1] }}
        </a>
    </div>
    <div v-else class="answer">
        <div v-if="winner == 'php'">
            <strong>PHP</strong>
            <p>PHP is oud, maar goud! Het wordt gebruikt op ruim 80% van alle websites. Dit komt door de vele Content Managemant Systemen zoals Wordpress. Ook kan het Web API's maken met Laravel.<br /> <br /> Wij raden je aan om het stappenplan 'Wordpress Developer' of het stappenplan 'Fullstack Developer' te bekijken.</p>
        </div>
        <div v-if="winner == 'javascript'">
            <strong>JavaScript</strong>
            <p>JavaScript is van origine een taal die websites interactief moest maken maar kan tegenwoordig veel meer. Zo kan je er Web API's, mobiele/desktop applicaties en Webautomatie mee maken.<br /> <br /> Wij raden je aan om het stappenplan 'Frontend Developer' of het stappenplan 'Fullstack Developer' te bekijken.</p>
        </div>
        <div v-if="winner == 'java'">
            <strong>Java</strong>
            <p>Java, vaak verward met JavaScript is een Object Georiënteerde programmeertaal. Het wordt gebruikt voor Web API's, Desktop Applicaties, IoT en nog veel meer. <br /> <br /> Wij raden je aan om het stappenplan 'Backend Developer' of het stappenplan 'Fullstack Developer' te bekijken.</p>
        </div>
        <div v-if="winner == 'csharp'">
            <strong>C#</strong>
            <p>C# of C Sharp is een door Microsoft ontwikkelde taal. Het wordt gebruikt voor Web API's, Desktop Applicaties, Web automatisering en nog veel meer. <br /> <br /> Wij raden je aan om het stappenplan 'Backend Developer' of het stappenplan 'Fullstack Developer' te bekijken.</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: "ScannerComponent",
    data() {
        return {
            current: 0,
            questions: {
                0: {
                    answer: undefined,
                    answers: {
                        0: "Geld verdienen",
                        1: "Wereld verbeteren"
                    }
                },
                1: {
                    answer: undefined,
                    answers: {
                        0: "Webapps of -sites",
                        1: "Mobiele Apps"
                    }
                },
                2: {
                    answer: undefined,
                    answers: {
                        0: "Wiskunde",
                        1: "Kunst en cultuur"
                    }
                },
                3: {
                    answer: undefined,
                    answers: {
                        0: "Midden- en kleinbedrijf",
                        1: "Multinationals"
                    }
                },
                4: {
                    answer: undefined,
                    answers: {
                        0: "Op kantoor",
                        1: "Thuiswerken"
                    }
                },
                5: {
                    answer: undefined,
                    answers: {
                        0: "Loondienst",
                        1: "Zelfstandige"
                    }
                }
            },
            result: {
                php: 0,
                javascript: 0,
                csharp: 0,
                java: 0,
            },
            winner: undefined
        }
    },
    methods: {
        setAnswer: function (answer) {
            this.questions[this.current].answer = answer;

            switch (this.current) {
                case 0:
                    if (answer == 0) {
                        // this.result.python = this.result.python + 1;
                        this.result.php = this.result.php + 1;
                        this.result.csharp = this.result.csharp + 1;
                    } else {
                        this.result.javascript = this.result.javascript + 1;
                        this.result.java = this.result.java + 1;
                    }
                    break;
                case 1:
                    if (answer == 0) {
                        this.result.php = this.result.php + 1;
                        this.result.javascript = this.result.javascript + 1;
                        this.result.csharp = this.result.csharp + 1;
                    } else {
                        this.result.java = this.result.java + 1;
                        this.result.javascript = this.result.javascript + 1;
                    }
                    break;
                case 2: 
                    if (answer == 0) {
                        // this.result.python = this.result.python + 1;
                        this.result.java = this.result.java + 1;
                    } else {
                        this.result.php = this.result.php + 1;
                        this.result.javascript = this.result.javascript + 1;
                    }
                    break;
                case 3: 
                    if (answer == 0) {
                        this.result.php = this.result.php + 1;
                        this.result.javascript = this.result.javascript + 1;
                    } else {
                        // this.result.python = this.result.python + 1;
                        this.result.java = this.result.java + 1;
                        this.result.csharp = this.result.csharp + 1;
                    }
                    break;
                case 4: 
                    if (answer == 0) {
                        // this.result.python = this.result.python + 1;
                        this.result.java = this.result.java + 1;
                    } else {
                        this.result.php = this.result.php + 1;
                        this.result.javascript = this.result.javascript + 1;
                        this.result.csharp = this.result.csharp + 1;
                    }
                case 5: {
                    if (answer == 0) {
                        this.result.csharp = this.result.csharp + 1;
                        this.result.python = this.result.python + 1;
                    } else {
                        this.result.php = this.result.php + 1;
                        this.result.javascript = this.result.javascript + 1;
                    }
                    break;
                }
            }

            this.current = this.current + 1;

            if (this.current == (Object.keys(this.questions).length)) {
                const languages = Object.keys(this.result);
                let winner = undefined;
                let score = 0;

                for (let i = 0; i < languages.length; i++) {
                    if (score < this.result[languages[i]]) {
                        score = this.result[languages[i]];
                        winner = languages[i];
                    }
                }

                this.winner = winner;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    .scanner {
        .question {
            padding: 10px 20px;
            a {
                padding: 8px 12px;
                background-color: #d4a373;
                font-weight: 600;
                text-transform: uppercase; 
                user-select: none;
                -webkit-user-select: none;
            }
            a:hover {
                background-color: #d09860;
                cursor: pointer;
            }
        }
        .answer {
            padding: 0px 20px;
        }
    }

    @media only screen and (max-width: 600px) {
        .scanner {
            .question {
                font-size: 12px;
            }
        }
    }
</style>