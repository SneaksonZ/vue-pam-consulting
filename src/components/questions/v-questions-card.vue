<template>
    <li class="questions-list-item">
        <div class="questions-list-item-header questions-list-item__header">
            <picture class="questions-list-item-header__picture">
                <img :src="require('../../assets/images/home/' + card.image)" alt='image'
                    class="questions-list-item-header__img">
                <span class="questions-list-item-header__tag questions-list-item-header-tag"> {{ card.tag }} </span>
            </picture>
        </div>
        <div class="questions-list-item__content questions-list-item-content">
            <h4 class="questions-list-item-content__title"> {{ card.title }}
            </h4>
            <p class="questions-list-item-content__text text"> {{ card.text }} </p>
        </div>
    </li>
</template>

<script>
export default {
    name: 'v-questions-card',
    components: {
    },
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>