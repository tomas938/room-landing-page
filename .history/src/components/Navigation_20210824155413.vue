<template>
	<nav class="navigation">
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
		<div class="navigation__logo">
			<img src="../../public/assets/logo.svg" alt="page-logo" />
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
	padding: 0 3rem;
	height: 8rem;
	background-color: transparent;
	display: flex;
	gap: 0rem;
	align-items: flex-end;
	@media screen and (min-width: 1000px) {
		gap: 8rem;
		padding: 0rem;
	}
	&__hamburger {
		cursor: pointer;
	}
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
	&__mobile__links {
		position: absolute;
		display: flex;
		justify-content: center;
		width: 100%;
		height: 8rem;
		background: white;
		a {
			text-decoration: none;
			font-size: 1.5rem;
			color: $black;
			font-weight: $bold;
		}
		ul {
			display: flex;
			gap: 4rem;
		}
		li {
			list-style: none;
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
</style>
