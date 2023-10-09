<template>
    <section class="questions">
        <div class="questions__body">
            <h2 class="questions__title title"> {{ title }} </h2>
            <swiper-container class="questions__list questions-list"
                :slides-per-view="3"
                :slides-per-group="3"
                :pagination-clickable="true"
            >
                    <swiper-slide class="questions__slide"
                        v-for="card in cards"
                        :key="card.id"
                    >
                        <v-questions-card 
                            :card="card"
                        />
                    </swiper-slide>
                </swiper-container>
           
        </div>
    </section>
</template>

<script>
import vQuestionsCard from './v-questions-card.vue';
import { register } from 'swiper/element/bundle';

register();


export default {
    name: 'v-questions',
    components: {
        vQuestionsCard
    },
    data() {
        return {
            title: 'Frequently Asked Questions',

            cards: [
                {
                    id: 'C0',
                    title: 'Question: How is the business environment in Cyprus?',
                    text: 'Answer: Cyprus is considered to be one of the most business-oriented countries of the EU, offering business entrepreneurs a variety of opportunities to expand their corporate dreams and ambitions.',
                    image: 'questions_slider_image.png',
                    tag: 'Business',
                },
                {
                    id: 'C1',
                    title: 'Question: What is the cost of living in Cyprus?',
                    text: 'Answer: In comparison to other countries of the EU, the cost of living is relatively low. Of course, the cost of living varies from city to city. For example, this means that living in Paphos might be a bit cheaper than living in Limassol.',
                    image: 'questions_slider_image.png',
                    tag: 'Prices'
                },
                {
                    id: "C2",
                    title: 'Question: What are the best cities in Cyprus for expats?',
                    text: 'Answer: As Cyprus is among the most attractive destinations for people from different parts of the globe, large and thriving expat communities can be found in Paphos, Limassol, Larnaca, Nicosia.',
                    image: 'questions_slider_image.png',
                    tag: 'Migration'
                },
                {
                    id: "C3",
                    title: 'Question: What is the Tax system like in Cyprus?',
                    text: 'Answer: With one of the lowest corporate tax rates (12.5%) in the European Union, the tax system is attractive to foreign investors. Neither succession taxes nor gains from the disposal of securities are subject to tax.',
                    image: 'questions_slider_image.png',
                    tag: 'Taxes'
                },
                {
                    id: "C4",
                    title: 'How long does it take to buy a property in Cyprus?',
                    text: 'Answer: The whole procedure for pur-chasing property in Cyprus should only take about 1-3 months. Of course, each situation is different and this timeframe may vary from one individual to another. Our relocation services aim to simplify this process by providing guidance and assistance from start to finish.',
                    image: 'questions_slider_image.png',
                    tag: 'Investment'
                },
                {
                    id: "C5",
                    title: 'Question: How long does it take to become a permanent resident in Cyprus?',
                    text: 'Answer: While a residency card can be obtained within two months through the fast-track process, a permanent resident of Cyprus can apply for Cyprus Citizenship after completing 5 years (1825 days) of legal stay in Cyprus, according to the naturalization scheme based on years of residence (M127). Once acquired, permanent residency in Cyprus is valid for life.',
                    image: 'questions_slider_image.png',
                    tag: 'Migration'
                },
                {
                    id: "C6",
                    title: 'Question: Is Cyprus a good country to live with a family?',
                    text: 'Answer: Cyprus is a perfect location for every type of family looking for a place to settle with their children. The stunning weather combined with great education programs, excellent healthcare system, and the ability to live in one of the safest countries in the world makes Cyprus a top choice among thousands every year.',
                    image: 'questions_slider_image.png',
                    tag: 'Family Relocation'
                },
                {
                    id: "C7",
                    title: 'Question: Does PAM Consulting offer any Investment Plans?',
                    text: 'Answer: Of course! Our services include the provision of a variety of investment opportunities you can choose from, depending on your needs and economic outlook.',
                    image: 'questions_slider_image.png',
                    tag: 'Invest in Cyprus'
                },
                {
                    id: "C8",
                    title: 'Question: Is Cyprus a member of the European Union (EU)?',
                    text: 'Answer: Yes, Cyprus has been a member of the EU since 2004. ',
                    image: 'questions_slider_image.png',
                    tag: 'Business'
                },
                {
                    id: "C9",
                    title: 'Question: Am I eligible to receive public healthcare if I am a permanent resident of Cyprus?',
                    text: 'Answer: Yes, you are. In accordance with National Legislation, Cyprus citizens with permanent residency rights and those whose ordinary residence is in an area controlled by the Cyprus Government are entitled to healthcare services under GHS.',
                    image: 'questions_slider_image.png',
                    tag: 'Migration'
                },
                {
                    id: "C10",
                    title: 'Question: Do my children have the option of attending a private or public school in Cyprus if I have a permanent residency?',
                    text: 'Answer: Yes. Public schools are free, while private educational institutions have tuition.',
                    image: 'questions_slider_image.png',
                    tag: 'Family Relocation'
                },
                {
                    id: "C11",
                    title: 'Question: How can I contact PAM Consulting?',
                    text: 'Answer: You can contact our team by simply visiting the “Contact Us” page, where you can find out contact details (email, telephone number) or fill in a form so we can get back to you as soon as possible.',
                    image: 'questions_slider_image.png',
                    tag: 'Migration'
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../../helpers/swiper-pagination.scss';
@import '../../helpers/functions.scss';

swiper-container::part(pagination) {
    right: 50%;
}

</style>