<template>
    <div class="boxes__card boxes-card">
        <picture class="boxes-card__icon">
            <img
                :src="require('../../../assets/images/boxes/' + card.image)"
                :alt="card.alt"
                class="boxes-card-icon__img"
            >
        </picture>
        <h4 class="boxes-card__title"> {{ card.title }} </h4>
        <p class="boxes-card__subtitle text"> {{ card.subtitle }} </p>
    </div>
</template>

<script>


export default {
    name: 'v-boxes-card',
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