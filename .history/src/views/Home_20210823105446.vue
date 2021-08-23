<template>
	<main class="intro">
		<header>
			<nav class="navigation">
				<div class="navigation__hamburger">
					<span></span>
					<span></span>
					<span></span>
				</div>
				<div class="navigation__links">
					<ul>
						<li><a href="#">home</a></li>
						<li><a href="#">shop</a></li>
						<li><a href="#">about</a></li>
						<li><a href="#">contact</a></li>
					</ul>
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
				across the country. Our experts combine form and function in bringing
				your vision to life. Create a room in your own style with our collection
				and make your property a reflection of you and what you love.
			</p>
			<div class="shop__link">
				<a href="#">shop now </a>
				<svg width="40" height="12" xmlns="http://www.w3.org/2000/svg">
					<path
						d="M34.05 0l5.481 5.527h.008v.008L40 6l-.461.465v.063l-.062-.001L34.049 12l-.662-.668 4.765-4.805H0v-1h38.206l-4.82-4.86L34.05 0z"
						fill="red	"
					/>
				</svg>
			</div>
		</section>
	</main>
	<section class="about">
		<img src="../assets/image-about-dark.jpg" alt="shop-image" />
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
			src="../assets/image-about-light.jpg"
			alt="about-image"
		/>
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
main {
	min-height: 60rem;
	grid-template-columns: 1fr 1fr;

	@media screen and (min-width: 1000px) {
		display: grid;
		grid-template-columns: 3fr 2fr;
	}
}
header {
	background-image: url("../assets/mobile-image-hero-1.jpg");
	@media screen and (min-width: 400px) {
		background-image: url("../assets/desktop-image-hero-1.jpg");
	}
	background-repeat: no-repeat;
	background-position: center center;
	background-size: cover;
	min-height: 36rem;
	position: relative;
}
.navigation {
	padding: 0 3rem;
	@media screen and (min-width: 1000px) {
		gap: 8rem;
		padding: 0rem;
	}
	height: 8rem;
	background-color: transparent;
	display: flex;
	gap: 0rem;
	align-items: flex-end;

	&__hamburger span {
		display: block;
		margin-top: 0.5rem;
		width: 3rem;
		height: 0.5rem;
		background-color: $white;
		@media screen and (min-width: 1000px) {
			display: none;
		}
	}
	&__links {
		display: none;
		@media screen and (min-width: 1000px) {
			display: block;
			order: 1;
		}
		ul {
			display: flex;
			gap: 4rem;
		}
		li {
			list-style: none;
		}
		a {
			text-decoration: none;
			color: $white;
			font-size: 1.6rem;
		}
	}
	&__logo {
		width: 100%;
		display: flex;
		justify-content: center;
		@media screen and (min-width: 1000px) {
			width: auto;
		}
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
//**  SHOP SECTION **//
///////////////////////
//**  SHOP SECTION **//
.shop {
	@media screen and (min-width: 1000px) {
		padding: 12rem 3.9rem;
	}
	h1 {
		font-size: 2.6rem;
		@media screen and (min-width: 1000px) {
			font-size: 3rem;
		}
		font-weight: $bold;
	}
	p {
		margin-top: 2rem;
		margin-bottom: 4rem;
		color: $dark-gray;
		line-height: 2rem;
		@media screen and (min-width: 1000px) {
			font-size: 1.6rem;
			line-height: 3rem;
		}
	}
	&__link {
		display: flex;
		align-items: center;
		gap: 2rem;
		&:hover {
			a {
				color: $dark-gray;
				transition: color 0.3s ease-in-out;
			}
		}
		a {
			letter-spacing: 1rem;
			font-size: 1.5rem;
			color: $black;
			text-decoration: none;
			text-transform: uppercase;
		}
	}
	svg path {
		fill: black;
		cursor: pointer;
	}
}

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
