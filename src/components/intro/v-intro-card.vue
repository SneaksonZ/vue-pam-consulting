<template>
    <div class="intro-cities-card intro-cities__card">
        <picture class="intro-cities-card-picture">
            <img v-bind:src="require('../../assets/images/home/' + card.image)" v-bind:alt="card.alt" class="intro-cities-card__img">
        </picture>
        <div class="intro-cities-card__subtitle"> {{ card.subtitle }} </div>
    </div>
</template>

<script>


export default {
    name: 'v-intro-card',
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