<template>
	<header>
		<nav class="navigation">
			<div class="navigation__hamburger">
				<span></span>
				<span></span>
				<span></span>
			</div>
			<div class="navigation__logo">
				<img src="../assets/logo.svg" alt="" />
			</div>
		</nav>
		<div class="sliders">
			<div class="slider slider-left">
				<img src="../assets/icon-angle-left.svg" alt="" />
			</div>
			<div class="slider slider-right">
				<img src="../assets/icon-angle-right.svg" alt="" />
			</div>
		</div>
	</header>
	<section class="shop">
		<h1>Discover innovative ways to decorate</h1>
		<p>
			We provide unmatched quality, comfort, and style for property owners
			across the country. Our experts combine form and function in bringing your
			vision to life. Create a room in your own style with our collection and
			make your property a reflection of you and what you love.
		</p>
		<div class="shop__link">
			<a href="#">shop now</a>
			<img src="/src/assets/icon-angle-right.svg" alt="" />
		</div>
	</section>
</template>

<script>
export default {
	name: "Home",
	components: {},
};
</script>
<style scoped lang="scss">
@import "/src/scss/variables";
header {
	background-image: url("../assets/mobile-image-hero-1.jpg");
	background-repeat: no-repeat;
	background-position: center center;
	background-size: cover;
	min-height: 36rem;
	position: relative;
}
.navigation {
	padding: 0 3rem;
	height: 8rem;
	background-color: transparent;
	display: flex;
	align-items: flex-end;
	&__hamburger span {
		display: block;
		margin-top: 0.5rem;
		width: 3rem;
		height: 0.5rem;
		background-color: $white;
	}
	&__logo {
		width: 100%;
		display: flex;
		justify-content: center;
	}
	img {
		width: 8rem;
		height: 2rem;
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
	}
}
.shop {
	h1 {
	}
	p {
	}
}
</style>
