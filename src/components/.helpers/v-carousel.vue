<template>
    <div class="carousel">
        <div class="carousel__body" :style="{ left: (-1 * itemWidth * currentItemIndex) + 'px'}" >
            <slot></slot>
        </div>
        <button @click="prevItem" :disabled="currentItemIndex === 0 && !isCyclic">Previous</button>
        <button @click="nextItem" :disabled="currentItemIndex === slides.length - 1 && !isCyclic">Next</button>
    </div>
</template>

<script>

export default {
    name: 'v-carousel',
    components: {
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
        pagination: {
            isEnabled: {
                type: Boolean,
                default() {
                    return false;
                },
            },
            classes: {
                type: String,
                default() {
                    return '';
                },
            },
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
            let vm = this;
            setInterval(function() {
                vm.nextItem();
            }, this.interval)
        }
    }
}
</script>

<style>

.carousel {
    width: 100%;
    height: 300;
    position: relative;
    overflow: hidden;
}

.carousel__body {
    min-width: auto;
    height: 300;
    display: flex;
    position: relative;
    align-items: stretch;
    transition: all .5s ease;
}




</style>