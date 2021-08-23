<template>
	<header>
		<nav class="navigation">
			<div class="navigation__hamburger">
				<span></span>
				<span></span>
				<span></span>
			</div>
			<div class="navigation__logo">
				<img src="../assets/logo.svg" alt="page-logo" />
			</div>
		</nav>
		<div class="sliders">
			<div class="slider slider-left">
				<img src="../assets/icon-angle-left.svg" alt="arrow-right" />
			</div>
			<div class="slider slider-right">
				<img src="../assets/icon-angle-right.svg" alt="arrow-right" />
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
			<img src="../assets/icon-arrow.svg" alt="arrow-right" />
		</div>
	</section>
	<img
		class="shop-image"
		src="../assets/image-about-dark.jpg"
		alt="shop-image"
	/>
	<section class="about">
		<h2>ABOUT OUR FURNITURE</h2>
		<p>
			Our multifunctional collection blends design and function to suit your
			individual taste.Make each room unique, or pick a cohesive theme that best
			express your interests and what inspires you. Find the furniture pieces
			you need, from traditional to contemporary styles or anything in between.
			Product specialists are available to help you create your dream space.
		</p>
	</section>
	<img
		class="about-image"
		src="../assets/image-about-light.jpg"
		alt="about-image"
	/>
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
	@media screen and (max-width: 400px) {
		background-image: url("../assets/mobile-image-hero-1.jpg");
	}
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
//**  SHOP SECTION **//
///////////////////////
//**  SHOP SECTION **//
.shop {
	h1 {
		font-size: 2.6rem;
		font-weight: $bold;
	}
	p {
		margin-top: 2rem;
		margin-bottom: 4rem;
		color: $dark-gray;
		line-height: 2rem;
	}
	&__link {
		display: flex;
		align-items: center;
		gap: 2rem;
		a {
			letter-spacing: 1rem;
			font-size: 1.5rem;
			color: $black;
			text-decoration: none;
			text-transform: uppercase;
		}
		img {
			width: 5rem;
			height: 2rem;
		}
	}
}
.shop-image,
.about-image {
	width: 100%;
	height: 100%;
}
//**  ABOUT SECTION **//
////////////////////////
//**  ABOUT SECTION **//
.about {
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
	}
}
</style>
