<template>
	<nav class="navigation">
		<div class="navigation__logo">
			<img src="../../public/assets/logo.svg" alt="page-logo" />
		</div>
		<div class="navigation__hamburger" @click="toggle()">
			<span></span>
			<span></span>
			<span></span>
		</div>
		<div class="navigation__mobile__links" :class="{ active }">
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
		return {
			active: false,
		};
	},
	methods: {
		toggle() {
			this.active = !this.active;
		},
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
	justify-content: space-between;
	gap: 0rem;
	@media screen and (min-width: 1000px) {
		justify-content: flex-start;
		gap: 7rem;
		padding: 0rem;
	}
	&__hamburger {
		cursor: pointer;
		display: block;
		z-index: 1000;
	}
	&__hamburger span {
		display: block;
		width: 3rem;
		height: 0.5rem;
		margin-top: 0.5rem;
		margin-right: 2rem;
		background-color: $black;
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
		margin-left: 2rem;

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
	transform: translateY(-100%);
	z-index: -10;
	position: absolute;
	background-color: $white;
	padding: 5rem 0;
	z-index: 10;
	width: 100%;
	display: block;
	order: 3;

	@media screen and (min-width: 1000px) {
		display: none;
	}
	ul {
		display: flex;
		gap: 4rem;
		@media only screen and (max-width: 650px) {
			gap: 1rem;
		}
	}
	li {
		list-style: none;
	}
	a {
		text-decoration: none;
		color: $black;
		font-weight: $bold;
		font-size: 1.6rem;
		@media only screen and (max-width: 650px) {
			font-size: 1.5rem;
		}
		@media only screen and (max-width: 400px) {
			font-size: 1.2rem;
		}
		&:first-child {
			margin-left: 4rem;
			@media only screen and (max-width: 500px) {
				margin-left: 2rem;
			}
			@media only screen and (max-width: 400px) {
				margin-left: 0.8rem;
			}
		}
	}
}
.navigation__mobile__links .active {
	transform: translateY(0%) !important;
}
</style>
