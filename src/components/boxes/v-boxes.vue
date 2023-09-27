<template>
    <section class="boxes">
        <div class="boxes__header">
            <h1 class="boxes__title title title_capitalize"> {{ block.title }} </h1>
            <p class="boxes__subtitle text"> {{ block.subtitle }} </p>
        </div>
        <div class="boxes__row boxes-row">
            <v-boxes-pair 
                v-for="pair in generatePairs"
                :key="pair.id"
                :pair="pair"
            />
        </div>
    </section>
</template>

<script>
import vBoxesPair from './v-boxes-pair.vue'

export default {
    name: 'v-boxes',

    components: {
        vBoxesPair
    },
    props: {
        block: {
            title: {
                type: String,
                default: ''
            },
            subtitle: {
                type: String,
                default: ''
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