<template>
	<main class="intro">
		<header
			:style="{
				backgroundImage: desktop
					? `url(${content[slide].imageDesktop})`
					: `url(${content[slide].imageMobile})`,
			}"
			:class="{ deactive: clicked, active: !clicked }"
		>
			<Navigation></Navigation>
			<Sliders
				@left-arrow-clicked="goLeft()"
				@right-arrow-clicked="goRight()"
			></Sliders>
		</header>
		<Shop
			:class="{ textdeactive: clicked, textactive: !clicked }"
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
			desktop: null,
			width: null,
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
				setTimeout(() => {
					this.slide === 2 ? (this.slide = 0) : this.slide++;
				}, 500);
				this.clicked = true;
				setTimeout(() => {
					this.clicked = false;
				}, 500);
			}
		},
		goLeft() {
			{
				if (!this.clicked) {
					setTimeout(() => {
						this.slide === 0 ? (this.slide = 2) : this.slide--;
					}, 500);
					this.clicked = true;
					setTimeout(() => {
						this.clicked = false;
					}, 500);
				}
			}
		},
	},
	mounted() {
		this.width = window.innerWidth;
		window.addEventListener("resize", () => {
			if (this.width < 400) {
				this.desktop = false;
				return;
			} else {
				this.desktop = true;
				return;
			}
		});
	},
};
</script>
<style lang="scss" scoped>
@import "/src/scss/variables";
// CONTENT ANIMATION //
.deactive {
	opacity: 0;
	transition: 0.45s ease-in-out;
}
.active {
	opacity: 1;
	transition: opacity 0.45s ease-in-out;
}
.textdeactive {
	opacity: 0;
	transform: translateX(100%);
	transition: 0.5s ease-in;
}
.textactive {
	opacity: 1;
	transition: all 0.9s ease-out;
}
main {
	overflow: hidden;
	min-height: 59.249rem;
	grid-template-columns: 1fr 1fr;
	@media screen and (min-width: 1000px) {
		display: grid;
		grid-template-columns: 3fr 2fr;
	}
}
header {
	min-height: 36rem;
	position: relative;
	background-repeat: no-repeat;
	background-size: cover;
	background-position: center;
}
</style>
