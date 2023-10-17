<template>
    <button
        class="button"
        :class="className"
        @click="click"
    >
        {{ title }}
    </button>
</template>

<script>
export default {
    name: "v-button",
    props: {
        title: {
            type: String,
            default: 'Find Out More'
        },
        isGradient: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        click() {
            this.$emit('click');
        }
    },
    computed: {
        className() {
            return {
                'button_gradient': this.isGradient
            }
        }
    }
}
</script>