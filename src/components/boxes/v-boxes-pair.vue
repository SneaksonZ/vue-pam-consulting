<template>
    <div class="boxes__row-pair">
        <v-boxes-card/>
    </div>
    <!-- <div class="boxes__card boxes-card">
        <picture class="boxes-card__icon">
            <img
                :src="require('../../assets/images/boxes/' + card.image)"
                :alt="card.alt"
                class="boxes-card-icon__img"
            >
        </picture>
        <h4 class="boxes-card__title"> {{ card.title }} </h4>
        <p class="boxes-card__subtitle text"> {{ card.subtitle }} </p>
    </div> -->
</template>

<script>
import vBoxesCard from './v-boxes-card.vue'

export default {
    name: 'v-boxes-pair',
    components: {
        vBoxesCard
    },
    props: {
        card: {
            type: Object,
            default() {
                return {};
            }
        }
    }
}
</script>