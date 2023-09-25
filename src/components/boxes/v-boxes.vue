<template>
		<section class="boxes">
			<div class="boxes__header">
				<h1 class="boxes__title title title_capitalize"> {{ block.title }} </h1>
				<p class="boxes__subtitle text"> {{ block.subtitle }} </p>
			</div>
			<div class="boxes__row boxes-row">
                <v-boxes-pair/>
				<div class="boxes__row-pair">
					<div class="boxes__card boxes-card">
						<picture class="boxes-card__icon">
							<img src="img/boxes/box_tax.png" alt="tax" class="boxes-card-icon__img">
						</picture>
						<h4 class="boxes-card__title">Progressive tax system</h4>
						<p class="boxes-card__subtitle text">Offering one of the most attractive tax regimes in
							Europe</p>
					</div>
					<div class="boxes__card boxes-card">
						<picture class="boxes-card__icon">
							<img src="img/boxes/box_weather-and-climate.png" alt="weather_and_climate"
								class="boxes-card-icon__img">
						</picture>
						<h4 class="boxes-card__title">Stunning weather and climate</h4>
						<p class="boxes-card__subtitle text">Enjoy a high quality of life with over 324 days of sun
							annually</p>
					</div>
				</div>
				<div class="boxes__row-pair">
					<div class="boxes__card boxes-card">
						<picture class="boxes-card__icon">
							<img src="img/boxes/box_expat-community.png" alt="expat_community"
								class="boxes-card-icon__img">
						</picture>
						<h4 class="boxes-card__title">Blooming expat community</h4>
						<p class="boxes-card__subtitle text">Become part of an increasingly diverse community</p>
					</div>
					<div class="boxes__card boxes-card">
						<picture class="boxes-card__icon">
							<img src="img/boxes/box_fimily-oriented.png" alt="family-oriented"
								class="boxes-card-icon__img">
						</picture>
						<h4 class="boxes-card__title">Family-oriented values</h4>
						<p class="boxes-card__subtitle text">Excellent education standards and extremely low crime
							rates</p>
					</div>
				</div>
			</div>
		</section>
</template>

<script>
import vBoxesPair from './v-boxes-pair.vue'

export default {
    name: 'v-boxes',
    
    components: {
        vBoxesPair
    },
    props: {
        block: {
            title: {
                type: String,
                default: ''
            },
            subtitle: {
                type: String,
                default: ''
            },
        },
        // boxes: {
        //     type: Object,
        //     default: {}
        // }
    },
    data() {
        return {
            boxes: [
                {
                    image: 'box_tax.png',
                    alt: 'tax',
                    title: 'Progressive tax system',
                    subtitle: 'Offering one of the most attractive tax regimes in Europe',
                },
                {
                    image: 'box_weather-and-climate.png',
                    alt: 'weather_and_climate',
                    title: 'Stunning weather and climate',
                    subtitle: 'Enjoy a high quality of life with over 324 days of sunannually',
                },
                {
                    image: 'box_expat-community.png',
                    alt: 'expat_community',
                    title: 'Blooming expat community',
                    subtitle: 'Become part of an increasingly diverse community',
                },
                {
                    image: 'box_fimily-oriented.png',
                    alt: 'family-oriented',
                    title: 'Family-oriented values',
                    subtitle: 'Excellent education standards and extremely low crime rates',
                }

            ]
        }
    },
    computed() {

    }     
}
</script>