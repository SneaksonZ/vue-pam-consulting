<template>
    <form class="contact-us-form" :method="block.method">
        <div class="contact-us-form__body">
            <h3 class="contact-us-form__title"> {{ block.title }} </h3>
            <div class="contact-us-form__inputs">
                <v-form-input
                    class="contact-us-form__input contact-us-form-input"
                    v-for="input in block.inputs"
                    :block="input"
                    :key="input.key"
                />
                <textarea type="text" class="contact-us-form__textarea contact-us-form-input" name="message"
                    placeholder="Your message" :tabindex="block.inputs.length + 1">
                </textarea>
            </div>
            <div class="contact-us-form__confirmation contact-us-form-confirmation" v-if="block.needsTermsConfirmation">
                <label class="checkbox contact-us-form__checkbox">
                    <input type="checkbox" class="contact-us-form__checkbox-input checkbox__input" :tabindex="block.inputs.length + 2">
                    <span class="checkbox__span contact-us-form__checkbox-span"></span>
                </label>
                <p class="contact-us-form-confirmation__text text">
                    By clicking "Submit button" you accept our
                    <a href="#" class="contact-us-form-confirmation__link">Terms & Conditions</a>
                    and have read our
                    <a href="#" class="contact-us-form-confirmation__link">Privacy Policy</a>
                    and
                    <a href="#" class="contact-us-form-confirmation__link">Disclaimer</a>
                </p>
            </div>
            <v-button
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