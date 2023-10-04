<template>
    <div class="carousel-item" :style="{'min-width': width + 'px'}">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'v-carousel-item',
    props: {
        data: {
            type: Object,
            default() {
                return {}
            }
        },
        width: {
            type: Number, 
            default: 300,
        }
    },
    data() {
        return {
        }
    },
    methods: {

    }
}
</script>