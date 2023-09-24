<template>
    <section class="intro">
        <div class="intro__body">
            <div class="intro__header">
                <div class="intro__tags intro-tags">
                    <v-intro-tag v-for="tag in tags" :key="tag.id" v-bind:tag="tag" />
                </div>
                <h1 class="intro__title title"> {{ intro.title }} </h1>
                <h4 class="intro__subtitle"> {{ intro.subtitle }} </h4>
                <p class="intro__text text"> {{ intro.text }} </p>
                <button class="intro__button button button_gradient">
                    Find Out More
                </button>
            </div>
            <div class="intro-cities">
                <h4 class="intro-cities__title title">Most popular cities</h4>
                <div class="intro-cities__row">
                    <v-intro-card v-for="card in cards" :key="card.id" v-bind:card="card" />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import vIntroTag from './v-intro-tag.vue'
import vIntroCard from './v-intro-card.vue'

export default {
    name: 'v-intro',
    components: {
        vIntroTag,
        vIntroCard
    },
    data() {
        return {
            intro: {
                title: 'Relocation to Cyprus',
                subtitle: 'Seamless - Exceptional - Experience',
                text: 'The captivating Mediterranean island of Cyprus has become a business haven with a flourishing expat community. The strategic location that grants networking opportunities and the stability of being in the EU offers entrepreneurs the abilities they need to thrive.'
            },
            tags: [
                {
                    id: 0,
                    text: 'Investments'
                },
                {
                    id: 1,
                    text: 'Business relocation'
                },
                {
                    id: 2,
                    text: 'Family relocation'
                }
            ],
            cards: [
                {
                    id: 0,
                    image: 'intro-cities_1.png',
                    alt: 'Nicosia',
                    subtitle: 'Nicosia'
                },
                {
                    id: 1,
                    image: 'intro-cities_2.png',
                    alt: 'Limassol',
                    subtitle: 'Limassol'
                },
                {
                    id: 2,
                    image: 'intro-cities_3.png',
                    alt: 'Paphos',
                    subtitle: 'Paphos'
                },
                {
                    id: 3,
                    image: 'intro-cities_4.png',
                    alt: 'Larnaka',
                    subtitle: 'Larnaka'
                }
            ]
        }
    }
}
</script>