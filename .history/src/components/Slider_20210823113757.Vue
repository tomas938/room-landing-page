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
						fill="black	"
					/>
				</svg>
			</div>
		</section>
	</main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
