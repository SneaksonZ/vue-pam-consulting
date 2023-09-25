<template>
    <section class="services">
        <div class="services__body">
            <h1 class="services__title title"> {{ block.title }} </h1>
            <div class="services__row">
                <v-services-card
                    v-for="card in cards"
                    :key="card.id"
                    :card="card"
                />
            </div>
        </div>
    </section>
</template>



<script>
import vServicesCard from './v-services-card.vue'

export default {
    name: 'v-services',
    components: {
        vServicesCard
    },
    data() {
        return {
            block: {
                title: 'Our Services'
            },
            cards: [
                {
                    id: 0,
                    image: 'services-cards_family-relocation.png',
                    alt: 'familyRelocation',
                    title: 'Family Relocation',
                    text: 'With strategic planning, we simplify the moving process so you and your family can feel safe and confident.'
                },
                {
                    id: 1,
                    image: 'services-cards_business-relocation.png',
                    alt: 'businessRelocation',
                    title: 'Business Relocation',
                    text: 'We handle the responsibility of moving your business to Cyprus, so you can focus on your business goals.'
                },
                {
                    id: 2,
                    image: 'services-cards_investment-schemes.png',
                    alt: 'InvestmentSchemes',
                    title: 'Investment Plans',
                    text: 'Discover the opportunity to further enhance your business ambitions, by choosing the optimal investment plan.'
                }
            ]
        }
    }
}
</script>