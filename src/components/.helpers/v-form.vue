<template>
    <form class="form" :method="block.method">
        <div class="form__body">
            <h3 class="form__title"> {{ block.title }} </h3>
            <div class="form__inputs">
                <v-form-input
                    class="form__input"
                    v-for="input in block.inputs"
                    :block="input"
                    :key="input.key"
                />
                <textarea type="text" class="form__textarea form-input" name="message"
                    placeholder="Your message" :tabindex="block.inputs.length + 1">
                </textarea>
            </div>
            <div class="form__confirmation form-confirmation" v-if="block.needsTermsConfirmation">
                <label class="checkbox form__checkbox">
                    <input type="checkbox" class="form__checkbox-input checkbox__input" :tabindex="block.inputs.length + 2">
                    <span class="checkbox__span form__checkbox-span"></span>
                </label>
                <p class="form-confirmation__text text">
                    By clicking "Submit button" you accept our
                    <a href="#" class="form-confirmation__link">Terms & Conditions</a>
                    and have read our
                    <a href="#" class="form-confirmation__link">Privacy Policy</a>
                    and
                    <a href="#" class="form-confirmation__link">Disclaimer</a>
                </p>
            </div>
            <v-button
                class="form__button"
                :title="block.button.title"
                :isGradient="block.button.isGradient"
            />
        </div>
    </form>
</template>

<script>
import vFormInput from './v-form-input';
import vButton from './v-button.vue';

export default {
    name: 'v-form',
    components: {
        vFormInput,
        vButton
    },
    props: {
        block: {
            type: Object,
            default() {
                return {}
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../../helpers/variables.scss';
@import '../../helpers/functions.scss';

.form {
    &__textarea {
        width: em(580);
        height: em(200);
    }
}

@media (max-width: px($widthMini)) {
    .form {
        &__textarea {
            width: 100%;
        }
    }
}
</style>