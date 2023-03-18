<template>
  <div class="scanner">
    <div class="question">
        {{ questions[0].question }}
    </div>
  </div>
</template>

<script>
export default {
    name: "ScannerComponent",
    data() {
        return {
            questions: {
                0: {
                    question: "Geld of Vrije tijd?",
                    answers: {
                        0: "Geld",
                        1: "Vrije tijd"
                    }
                },
                1: {
                    question: "Web of Mobile?",
                    answers: {
                        0: "Web",
                        1: "Mobile"
                    }
                },
                2: {
                    question: "Geld of Vrije tijd?",
                    answers: {
                        0: "Geld",
                        1: "Vrije tijd"
                    }
                }
            }
        }
    }
}
</script>

<style>

</style>