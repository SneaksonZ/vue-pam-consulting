<template>
    <v-boxes
        :block="block"
        :cards="boxes"
    />
</template>

<script>
import vBoxes from './v-boxes.vue';

export default {
    name: 'v-make-it-happen',
    components: {
        vBoxes
    },
    data() {
        return {
            block: {
                title: 'How we make it happen',
            },
            boxes: [
                {
                    image: 'box_listen.png',
                    alt: 'listen',
                    title: 'We listen',
                    subtitle: 'Our most prominent purpose is to understand and identify with your needs so we can effectively find ways to provide solutions.',
                },
                {
                    image: 'box_strategize.png',
                    alt: 'strategize',
                    title: 'We strategize',
                    subtitle: 'According to your requirements, our team designs a thorough series of steps that will make the relocation process as smooth as possible.',
                },
                {
                    image: 'box_provide.png',
                    alt: 'provide',
                    title: 'We provide',
                    subtitle: 'We implement our services that are based on efficient strategic planning that respond to your family\'s and business\'s goals and ambitions.',
                },
                {
                    image: 'box_manage.png',
                    alt: 'we_manage',
                    title: 'We manage',
                    subtitle: 'Once you are settled, we make sure that everything is according to your expectations and your vision of the quality of our services.',
                },

            ]
        }
    },
}
</script>