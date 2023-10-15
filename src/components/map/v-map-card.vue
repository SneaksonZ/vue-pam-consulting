<template>
    <div class="map__card map-card">
        <div class="map-card-header">
            <div class="map-card-header__images-row">
                <picture
                    class="map-card-header-picture map-card-header__picture"
                    v-for="image in card.images"
                    :key="image.key"
                >
                    <img
                        class="map-card-header__img"
                        :src="require('../../assets/images/home/' + image.src)"
                        :alt="image.alt"
                    >
                </picture>
            </div>
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