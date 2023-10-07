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
            @goToPage="goToPage($event - 1)"
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
            isAutoswipePaused: false,
            intervalId: 0,
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
                return false;
            },
        },
        swipeInterval: {
            type: Number,
            default() {
                return 0;
            }
        },
        onClickInterval: {
            type: Number,
            default() {
                return this.swipeInterval;
            }
        },
        pagination: {
            type: Object,
            default() {
                return {
                    isEnabled: false,
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
        goToPage(pageIndex) {
            this.currentItemIndex = pageIndex;
            this.setSwipeInterval(this.onClickInterval, true);
        },
        setSwipeInterval(interval, isTemprary = false) { // isTemprary if timeout uses only once, then replaces by default timeout
            clearInterval(this.intervalId); 
            this.intervalId = setInterval(() => {
                this.nextItem();
                if (isTemprary)
                    this.setSwipeInterval(this.swipeInterval, false)
            }, interval);
        }
    },
    mounted() {
        if (this.swipeInterval > 0) {
            this.setSwipeInterval(this.swipeInterval);
        }
    }
}
</script>
