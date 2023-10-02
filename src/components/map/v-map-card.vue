<template>
    <div class="map__card map-card">
        <div class="map-card__images-row map-card-images-row">
            <img
                v-for="image in card.images"
                class="map-card__img"
                :key="image.key"
                :src="require('../../assets/images/home/' + image.src)"
                :alt="image.alt"
            >
        </div>
        <h4 class="map-card__title"> {{ card.title }} </h4>
        <p class="map-card__text text" v-html="card.text" ></p>
    </div>
</template>

<script>
    export default {
        name: 'v-map-card',
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