<template>
	<div class="sliders">
		<button class="slider slider-left" @click="$emit('LeftArrowClicked')">
			<img src="../../public/assets/icon-angle-left.svg" alt="arrow-right" />
		</button>
		<button class="slider slider-right" @click="$emit('RightArrowClicked')">
			<img src="../../public/assets/icon-angle-right.svg" alt="arrow-right" />
		</button>
	</div>
</template>

<style lang="scss" scoped>
@import "/src/scss/variables";
button {
	border: none;
	outline: none;
	background-color: $black;
	&:focus {
		border: 1px dotted $white;
	}
}
.sliders {
	position: absolute;
	bottom: 0;
	right: 0;
	display: flex;
	background-color: $black;
	width: 11rem;
	height: 5.5rem;
	@media screen and (min-width: 1000px) {
		right: -15rem;
		width: 15rem;
		height: 7.5rem;
	}
}
.slider {
	cursor: pointer;
	display: flex;
	justify-content: center;
	align-items: center;
	width: 100%;
	height: 100%;
	img {
		width: 1.5rem;
		height: 2rem;
		@media screen and (min-width: 1000px) {
			width: 2rem;
			height: 3rem;
		}
	}
}
.slider-left:hover,
.slider-right:hover {
	background-color: $very-dark-gray;
	transition: background-color 0.3s ease-in-out;
}
</style>
