<template>
    <ul class="carousel__pagination carousel-pagination carousel-pagination_vertical"
    >
        <li v-for="page in totalPages"
            :key="page"
            class="carousel-pagination__item_vertical carousel-pagination-item"
            :class="{ 'carousel-pagination-item_active' : page === currentPage }"
            @click="goToPage(page)"
        ></li>
    </ul>
</template>

<script>

export default {
    name: 'v-carousel-pagination',
    props: {
        currentPage: {
            type: Number,
            default: 0
        },
        totalItems: {
            type: Number,
            required: true,
        },
        itemsPerPage: {
            type: Number,
            default() {
                return 1;
            }
        }
    },
    methods: {
        goToPage(page) {
            this.$emit('goToPage', page);
        }
    },
    computed: {
        totalPages() {
            return Math.ceil(this.totalItems / this.itemsPerPage);
        }
    }
}
</script>
