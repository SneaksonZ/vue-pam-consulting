<template>
    <section class="contact-us">
        <div class="container">
            <div class="contact-us__wrapper">
                <v-title
                    class="contact-us__title"
                    :text="block.title"
                    :needsUnderline="true"
                />
                <div class="contact-us-contacts contact-us__contacts">
                    <div class="contact-us-contacts__column" v-for="icon in block.icons" :key="icon.key">
                        <img :src="require('../../assets/images/home/' + icon.src)"  :alt="icon.alt" class="contact-us-contacts__icon">
                        <span class="contact-us-contacts__subtitle"> {{ icon.subtitle }} </span>
                    </div>
                </div>
                <v-form
                    :block="block.form"
                />
            </div>
        </div>
    </section>
</template>



<script>
import vTitle from '../.helpers/v-title.vue';
import vForm from '../.helpers/v-form.vue';

export default {
    name: 'v-contact-us',
    components: {
        vTitle,
        vForm
    },
    data() {
        return {
            block: {
                title: 'Contact Us',
                icons: [
                    {
                        src: 'contact-us_phone-icon.svg',
                        alt: 'phone_icon',
                        subtitle: '+357 9056759'
                    },
                    {
                        src: 'contact-us_mail-icon.svg',
                        alt: 'mail_icon',
                        subtitle: 'contact@pamrelocation.com'
                    }
                ],
                form: {
                    title: 'SEND INQUIRY',
                    method: 'post',
                    inputs: [
                        {
                            type: 'text',
                            name: 'name',
                            placeholder: 'Your Name',
                            tabindex: '1'
                        },
                        {
                            type: 'email',
                            name: 'email',
                            placeholder: 'Email',
                            tabindex: '2'
                        },
                        {
                            type: 'text',
                            name: 'subject',
                            placeholder: 'Subject',
                            tabindex: '3'
                        },
                        {
                            type: 'tel',
                            name: 'phone',
                            placeholder: 'Phone',
                            tabindex: '4'
                        },
                    ],
                    needsTermsConfirmation: true,
                    button: {
                        title: 'Submit',
                        isGradient: false
                    }
                }
            },
        }
    }
}
</script>