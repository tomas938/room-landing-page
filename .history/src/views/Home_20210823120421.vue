<template>
	<Header></Header>
	<
</template>

<script>
import Header from "../components/Header";
export default {
	components: {
		Header,
	},
};
</script>
<style scoped lang="scss">
@import "/src/scss/variables";
//**  ABOUT SECTION **//
////////////////////////
//**  ABOUT SECTION **//
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
