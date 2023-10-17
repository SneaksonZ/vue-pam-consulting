<template>
    <div class="boxes-row-pair">
        <v-boxes-card
            class="boxes__card"
            v-for="card in pair"
            :key="card.id"
            :card="card"
        />
    </div>
</template>

<script>
import vBoxesCard from './v-boxes-card.vue'

export default {
    name: 'v-boxes-pair',
    components: {
        vBoxesCard
    },
    props: {
        pair: {
            type: Array,
            default() {
                return [];
            }
        }
    },
}
</script>