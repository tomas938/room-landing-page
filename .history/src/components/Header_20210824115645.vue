<template>
	<main class="intro" v-if="slide === 0">
		<header :style="{ backgroundImage: `url(${content[slide].imageDesktop})` }">
			<Navigation></Navigation>
			<Sliders
				@left-arrow-clicked="goLeft()"
				@right-arrow-clicked="goRight()"
			></Sliders>
		</header>
		<Shop
			:class="{ deactive: clicked, active: !clicked }"
			:heading="content[slide].heading"
			:description="content[slide].description"
		></Shop>
	</main>
	<main class="intro" v-if="slide === 1">
		<header :style="{ backgroundImage: `url(${content[slide].imageDesktop})` }">
			<Navigation></Navigation>
			<Sliders
				@left-arrow-clicked="goLeft()"
				@right-arrow-clicked="goRight()"
			></Sliders>
		</header>
		<Shop
			:class="{ deactive: clicked, active: !clicked }"
			:heading="content[slide].heading"
			:description="content[slide].description"
		></Shop>
	</main>
	<main class="intro" v-if="slide === 2">
		<header :style="{ backgroundImage: `url(${content[slide].imageDesktop})` }">
			<Navigation></Navigation>
			<Sliders
				@left-arrow-clicked="goLeft()"
				@right-arrow-clicked="goRight()"
			></Sliders>
		</header>
		<Shop
			:class="{ deactive: clicked, active: !clicked }"
			:heading="content[slide].heading"
			:description="content[slide].description"
		></Shop>
	</main>
</template>

<script>
import Shop from "./Shop";
import Navigation from "./Navigation";
import Sliders from "./Sliders.vue";
export default {
	components: {
		Shop,
		Navigation,
		Sliders,
	},
	data() {
		return {
			slide: 0,
			clicked: false,
			content: [
				{
					heading: "Discover innovative ways to decorate ",
					description:
						"We provide unmatched quality, comfort, and style for property owners across the country. Our experts combine form and function in bringing your vision to life. Create a room in your own style with our collection and make your property a reflection of you and what you love.",
					imageDesktop: "../assets/desktop-image-hero-1.jpg",
					imageMobile: "../assets/mobile-image-hero-1.jpg",
				},
				{
					heading: "We are available all across the globe",
					description:
						"With stores all over the world, it's easy for you to find furniture for your home or place of business. Locally, we’re in most major cities throughout the country. Find the branch nearest you using our store locator. Any questions? Don't hesitate to contact us today.",
					imageDesktop: "../assets/desktop-image-hero-2.jpg",
					imageMobile: "../assets/mobile-image-hero-2.jpg",
				},
				{
					heading: "Manufactured with the best materials ",
					description:
						" Our modern furniture store provide a high level of quality. Our company has invested in advanced technology to ensure that every product is made as perfect and as consistent as possible. With three decades of experience in this industry, we understand what customers want for their home and office. ",
					imageDesktop: "../assets/desktop-image-hero-3.jpg",
					imageMobile: "../assets/mobile-image-hero-3.jpg",
				},
			],
		};
	},
	methods: {
		goRight() {
			if (!this.clicked) {
				this.slide === 2 ? (this.slide = 0) : this.slide++;
				this.clicked = true;
				setTimeout(() => {
					this.clicked = false;
				}, 500);
			}
		},
		goLeft() {
			{
				if (!this.clicked) {
					this.slide === 0 ? (this.slide = 2) : this.slide--;
					this.clicked = true;
					setTimeout(() => {
						this.clicked = false;
					}, 500);
				}
			}
		},
	},
};
</script>
<style lang="scss" scoped>
@import "/src/scss/variables";
// CONTENT ANIMATION //
.deactive {
	opacity: 0;
}
.active {
	opacity: 1;
	transition: opacity 0.45s ease-in-out;
}
main {
	min-height: 59.249rem;
	grid-template-columns: 1fr 1fr;
	@media screen and (min-width: 1000px) {
		display: grid;
		grid-template-columns: 3fr 2fr;
	}
}
header {
	background: url("../../public/assets/desktop-image-hero-1.jpg") no-repeat -9999px -9999px;
	background: url("../../public/assets/desktop-image-hero-2.jpg") no-repeat -9999px -9999px;
	background: url("../../public/assets/desktop-image-hero-3.jpg") no-repeat -9999px -9999px;
	transition: 0.45s ease-in-out;
	min-height: 36rem;
	position: relative;
	background-repeat: no-repeat;
	background-size: cover;
	background-position: center;
}
</style>
