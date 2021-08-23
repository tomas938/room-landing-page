<template>
	<main class="intro">
		<header
			:style="{
				backgroundImage: `url(${content[slide].imageDesktop})`,
			}"
		>
			<Navigation></Navigation>
			<Sliders.
			<!-- <div class="sliders">
				<div class="slider slider-left" @click="goLeft()">
					<img
						src="../../public/assets/icon-angle-left.svg"
						alt="arrow-right"
					/>
				</div>

				<div class="slider slider-right" @click="goRight()">
					<img
						src="../../public/assets/icon-angle-right.svg"
						alt="arrow-right"
					/>
				</div>
			</div> -->
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
	transition: background-image 0.45s ease-in-out;
	min-height: 36rem;
	position: relative;
	background-repeat: no-repeat;
	background-size: cover;
	background-position: center;
}
// .sliders {
// 	position: absolute;
// 	bottom: 0;
// 	right: 0;
// 	display: flex;
// 	background-color: $black;
// 	width: 11rem;
// 	height: 5.5rem;
// 	@media screen and (min-width: 1000px) {
// 		right: -15rem;
// 		width: 15rem;
// 		height: 7.5rem;
// 	}
// }
// .slider {
// 	cursor: pointer;
// 	display: flex;
// 	justify-content: center;
// 	align-items: center;
// 	width: 100%;
// 	height: 100%;
// 	img {
// 		width: 1.5rem;
// 		height: 2rem;
// 		@media screen and (min-width: 1000px) {
// 			width: 2rem;
// 			height: 3rem;
// 		}
// 	}
// }
// .slider-left:hover,
// .slider-right:hover {
// 	background-color: $very-dark-gray;
// 	transition: background-color 0.3s ease-in-out;
// }
</style>
