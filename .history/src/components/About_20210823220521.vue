<template>
	<section class="about">
		<img src="../../public/assets/image-about-dark.jpg" alt="shop-image" />
		<div class="about__content">
			<h2>ABOUT OUR FURNITURE</h2>
			<p>
				Our multifunctional collection blends design and function to suit your
				individual taste.Make each room unique, or pick a cohesive theme that
				best express your interests and what inspires you. Find the furniture
				pieces you need, from traditional to contemporary styles or anything in
				between. Product specialists are available to help you create your dream
				space.
			</p>
		</div>
		<img
			class="about-image"
			src="../../public/assets/image-about-light.jpg"
			alt="about-image"
		/>
	</section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "/src/scss/variables";
.about {
	padding: 0;
	display: grid;
	justify-items: center;
	align-items: center;
	grid-template-columns: 1fr;
	@media screen and (min-width: 1000px) {
		grid-template-columns: 1fr 2fr 1fr;
	}
	&__content {
		display: flex;
		flex-direction: column;
		@media screen and (min-width: 1000px) {
			font-size: 1.6rem;
			padding: 11rem 5rem;
		}
		padding: 8rem 2rem;
	}
	h2 {
		font-size: 1.4rem;
		letter-spacing: 0.45rem;
		font-weight: $bold;
	}
	p {
		margin-top: 2rem;
		margin-bottom: 4rem;
		color: $dark-gray;
		line-height: 2rem;
		@media screen and (min-width: 1000px) {
			line-height: 3rem;
			margin-bottom: 0rem;
		}
	}
	img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}
}
</style>
