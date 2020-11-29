<template>
    <b-carousel>
        <b-carousel-item v-for="(carousel, i) in carousels" :key="i">
            <section :class="`hero is-medium is-${carousel.color}`">
                <div class="hero-body has-text-centered">
                    <h1 class="title">{{carousel.text}}</h1>
                </div>
            </section>
        </b-carousel-item>
    </b-carousel>
</template>

<script>
export default {
    data(){
        return {
            carousels: [
                { text: 'Massaman Curry', color: 'primary' },
                { text: 'Neapolitan Pizza', color: 'info' },
                { text: 'Mexican Hot Chocolate', color: 'success' },
                { text: 'Japanese sushi', color: 'warning' },
                { text: 'Chinese Peking Duck', color: 'danger' }
            ]
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
