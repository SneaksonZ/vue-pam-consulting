<template>
    <section class="services">
        <div class="container">
            <v-title class="services__title"
                :text="block.title"
                :needsUnderline="true"
            />
            <ul class="services__row">
                <li class="services__item"
                    v-for="card in cards"
                    :key="card.id"
                >
                    <v-services-card
                        :card="card"
                    />
                </li>
            </ul>
        </div>
    </section>
</template>


<script>
import vTitle from '../.helpers/v-title.vue';
import vServicesCard from './v-services-card.vue';

export default {
    name: 'v-services',
    components: {
        vTitle,
        vServicesCard,
    },
    data() {
        return {
            block: {
                title: 'Our Services',
            },
            cards: [
                {
                    id: 0,
                    image: 'services-cards_family-relocation.jpg',
                    alt: 'familyRelocation',
                    title: 'Family Relocation',
                    text: 'With strategic planning, we simplify the moving process so you and your family can feel safe and confident.',
                },
                {
                    id: 1,
                    image: 'services-cards_business-relocation.jpg',
                    alt: 'businessRelocation',
                    title: 'Business Relocation',
                    text: 'We handle the responsibility of moving your business to Cyprus, so you can focus on your business goals.',
                },
                {
                    id: 2,
                    image: 'services-cards_investment-schemes.jpg',
                    alt: 'investmentSchemes',
                    title: 'Investment Plans',
                    text: 'Discover the opportunity to further enhance your business ambitions, by choosing the optimal investment plan.',
                },
            ]
        }
    }
}
</script>