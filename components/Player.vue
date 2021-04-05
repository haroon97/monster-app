<template>
    <div class="container">
        <h4>{{ name }}</h4>
        <b-progress :max="100" :value="value" show-progress animated :variant="name === 'User' ? 'success' : 'danger'"></b-progress>
    </div>
</template>

<script>
    export default {
        mounted() {
            if (this.name === 'User') {
                this.$nuxt.$on('attack', () => {
                    this.value -= this.generateRandomNumber();
                    this.$nuxt.$emit('monsterTurn');
                })
            }
            else {
                this.$nuxt.$on('monsterTurn', () => {
                    this.value -= this.generateRandomNumber();
                })
            }
        },
        data() {
            return {
                value: 100
            }
        },
        methods: {
            generateRandomNumber: () => {
                return  Math.floor(Math.random() * 11) + 1;
            }
        },
        props: {
            name: {
                type: String,
                default: 'User'
            }
        }
    }
</script>

<style scoped>

</style>