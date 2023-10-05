<template>
    <div class="carousel">
        <div class="carousel__wrapper">
            <div class="carousel__body" :style="{ left: (-1 * itemWidth * currentItemIndex) + 'px'}" >
                <slot></slot>
            </div>
        <!-- <button @click="prevItem" :disabled="currentItemIndex === 0 && !isCyclic">Previous</button> -->
        <!-- <button @click="nextItem" :disabled="currentItemIndex === slides.length - 1 && !isCyclic">Next</button> -->
        </div>
        <v-carousel-pagination 
            v-if="pagination.isEnabled"
            :class="pagination.classes"
            :totalItems="slides.length"
            :itemsPerPage="1"
            :currentPage="currentItemIndex + 1"
            @goToPage="currentItemIndex = $event - 1"
        />
    </div>
</template>

<script>
import vCarouselPagination from './v-carousel-pagination.vue';

export default {
    name: 'v-carousel',
    components: {
        vCarouselPagination
    },
    data() {
        return {
            currentItemIndex: 0,
            slides: this.$slots.default,
        }
    },
    props: {
        itemWidth: {
            type: Number,
            default() {
                return 200;
            },
        },
        isCyclic: {
            type: Boolean,
            default() {
                return true;
            },
        },
        interval: {
            type: Number,
            default() {
                return 0;
            }
        },
        pagination: {
            type: Object,
            default() {
                return {
                    isEnabled: true,
                    classes: '',
                }
            }
        }
        
    },
    methods: {
        nextItem() {
            this.currentItemIndex++;
            if (this.currentItemIndex >= this.slides.length)
                this.isCyclic ? this.currentItemIndex = 0 : this.currentItemIndex = this.slides.length - 1;
        },
        prevItem() {
            this.currentItemIndex--;
            if (this.currentItemIndex < 0)
                this.isCyclic ? this.currentItemIndex = this.slides.length - 1 : this.currentItemIndex = 0;
        },
    },
    mounted() {
        if (this.interval > 0) {
            setInterval(() => {
                this.nextItem();
            }, this.interval);
        }
    }
}
</script>
