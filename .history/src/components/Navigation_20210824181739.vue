<template>
	<nav class="navigation">
		<div class="navigation__logo">
			<img src="../../public/assets/logo.svg" alt="page-logo" />
		</div>
		<div class="navigation__hamburger">
			<span></span>
			<span></span>
			<span></span>
		</div>
		<div class="navigation__mobile__links">
			<ul>
				<li><a href="#">home</a></li>
				<li><a href="#">shop</a></li>
				<li><a href="#">about</a></li>
				<li><a href="#">contact</a></li>
			</ul>
		</div>
		<div class="navigation__desktop__links">
			<ul>
				<li><a href="#">home</a></li>
				<li><a href="#">shop</a></li>
				<li><a href="#">about</a></li>
				<li><a href="#">contact</a></li>
			</ul>
		</div>
	</nav>
</template>

<script>
export default {
	data() {
		return {};
	},
};
</script>

<style lang="scss" scoped>
@import "/src/scss/variables";
.navigation {
	width: 100%;
	height: 8rem;
	background-color: transparent;
	position: relative;
	display: flex;
	align-items: flex-end;
	justify-content: space-around;
	gap: 0rem;
	@media screen and (min-width: 1000px) {
		gap: 8rem;
		padding: 0rem;
	}
	&__hamburger {
		cursor: pointer;
	}
	&__hamburger span {
		display: block;
		width: 3rem;
		height: 0.5rem;
		margin-top: 0.5rem;
		background-color: $white;
		order: 1;
		@media screen and (min-width: 1000px) {
			display: none;
		}
	}
	&__desktop__links {
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
		@media screen and (min-width: 1000px) {
			margin-left: 4rem;
			width: auto;
		}
	}
	img {
		@media screen and (min-width: 1000px) {
			display: block;
		}
		width: 8rem;
		height: 2rem;
	}
}

.navigation__mobile__links {
	top: 10%;
	position: absolute;
	background-color: white;
	z-index: 10;
	width: 100%;
	display: block;
	order: 3;

	@media screen and (min-width: 1000px) {
		display: none;
	}
	ul {
		display: flex;
	}
	li {
		list-style: none;
	}
	a {
		text-decoration: none;
		color: $black;
		font-weight: $bold;
		font-size: 1.6rem;
	}
}
</style>
