<template>
<div class="box" id="pica">
    <div>
    <h1>Ovdje se nalaze recepti za pića i koktele.</h1>
    </div>
    <div>
    <section>

        <b-collapse
            class="card"
            animation="slide"
            v-for="(collapse, index) of collapses"
            :key="index"
            :open="isOpen == index"
            @open="isOpen = index">
            <div
                slot="trigger"
                slot-scope="props"
                class="card-header"
                role="button">
                <p class="card-header-title">
                    {{ collapse.title }}
                </p>
                <a class="card-header-icon">
                    <b-icon
                        :icon="props.open ? 'menu-down' : 'menu-up'">
                    </b-icon>
                </a>
            </div>
            <div class="card-content">
                <div class="content">
                    {{ collapse.text }}
                </div>
            </div>
        </b-collapse>

    </section>

    </div>
</div>
</template>
<script>
    export default {
        data() {
            return {
                isOpen: 0,
                collapses: [
                {
                    title: 'Recept 1',
                    text: 'Opis 1'
                },
                {
                    title: 'Recept 2',
                    text: 'Opis 2'
                },
                {
                    title: 'Recept 3',
                    text: 'Opis 3'
                }
                ]
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
