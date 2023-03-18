<template>
  <div class="data">
    <div class="heading">
        <h2>
            Liever cijfers over programmeren bekijken?
        </h2>
        <div class="visualized">
            <div class="trending">
                <div 
                v-for="item in trending"
                v-bind:key="item">
                    {{ item.name }}
                    {{ item.ratings }}%
                </div>
            </div>
            <div class="careers">

            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: "DataComponent",
    data() {
        return {
            trending: {
                0: {
                    name: "Python",
                    ratings: 14.83
                },
                1: {
                    name: "C",
                    ratings: 14.73
                },
                2: {
                    name: "Java",
                    ratings: 13.56
                }
            },
            careers: {
                0: {
                    name: "Full Stack Developer",
                    annual_earnings: 14.83
                },
                1: {
                    name: "C",
                    ratings: 14.73
                },
                2: {
                    name: "Java",
                    ratings: 13.56
                }
            }
        }
    }
}
</script>

<style lang="scss" scoped>

</style>