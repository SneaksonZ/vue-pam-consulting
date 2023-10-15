<template>
    <section class="boxes">
        <div class="container boxes__container">
            <div class="boxes__wrapper">
                <div class="boxes__header">
                    <v-title
                        class="boxes__title"
                        :needsMobileCapitalize="block.title.mobileCapitalize"
                        :text="block.title.text"
                    />
                    </h1>
                    <p class="boxes__subtitle text"> {{ block.subtitle }} </p>
                </div>
                <div class="boxes__row boxes-row">
                    <v-boxes-pair 
                        v-for="pair in generatePairs"
                        :key="pair.id"
                        :pair="pair"
                    />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import vTitle from '../v-title.vue';
import vBoxesPair from './v-boxes-pair.vue'

export default {
    name: 'v-boxes',

    components: {
        vTitle,
        vBoxesPair
    },
    props: {
        block: {
            title: {
                text: { type: String,
                default: ''
                },
                mobileCapitalize: {
                    type: Boolean,
                    default: false,
                },
            },
            subtitle: {
                type: String,
                default: '',
            },
        },
        cards: {
            type: Array,
            default() {
                return [];
            }
        }
    },
    computed: {
        generatePairs() {
            var cardPairs = new Array;
            for (var i = 0; i < this.cards.length; i += 2) {
                var temp = new Array;
                temp.push(this.cards[i]);
                if (i != this.cards.length - 1)
                    temp.push(this.cards[i + 1]);
                cardPairs.push(temp);
            }
            return cardPairs;
        }
    }
}
</script>