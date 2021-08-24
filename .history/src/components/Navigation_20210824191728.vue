<template>
	<header>
		<nav class="navigation">
			<a class="navigation__logo">
				<img src="../../public/assets/logo.svg" alt="" />
			</a>
			<div class="navigation__links">
				<ul v-show="!mobile">
					<li>
						<router-link class="link" :to="{ name: 'Home' }">home</router-link>
					</li>
					<li>
						<router-link class="link" :to="{ name: 'Home' }">shop</router-link>
					</li>
					<li>
						<router-link class="link" :to="{ name: 'Home' }">about</router-link>
					</li>
					<li>
						<router-link class="link" :to="{ name: 'Home' }"
							>contact</router-link
						>
					</li>
				</ul>
			</div>

			<div
				class="navigation__hamburger"
				@click="toggleMobileNav"
				v-show="mobile"
			>
				<svg class="line" width="60" height="60" viewBox="0 0 100 100">
					<path
						class="line line1"
						:class="{ active: mobileNav }"
						d="M 20,29.000046 H 80.000231 C 80.000231,29.000046 94.498839,28.817352 94.532987,66.711331 94.543142,77.980673 90.966081,81.670246 85.259173,81.668997 79.552261,81.667751 75.000211,74.999942 75.000211,74.999942 L 25.000021,25.000058"
					/>
					<path
						class="line line2"
						:class="{ active: mobileNav }"
						d="M 20,50 H 80"
					/>
					<path
						class="line line3"
						:class="{ active: mobileNav }"
						d="M 20,70.999954 H 80.000231 C 80.000231,70.999954 94.498839,71.182648 94.532987,33.288669 94.543142,22.019327 90.966081,18.329754 85.259173,18.331003 79.552261,18.332249 75.000211,25.000058 75.000211,25.000058 L 25.000021,74.999942"
					/>
				</svg>
			</div>
		</nav>
		<div>
			<ul
				class="mobile__links"
				:class="{ active: mobileNav }"
				v-show="mobileNav"
			>
				<li>
					<router-link class="link" :to="{ name: 'Home' }">home</router-link>
				</li>
				<li>
					<router-link class="link" :to="{ name: 'Home' }">shop</router-link>
				</li>
				<li>
					<router-link class="link" :to="{ name: 'Home' }">about</router-link>
				</li>
				<li>
					<router-link class="link" :to="{ name: 'Home' }">contact</router-link>
				</li>
			</ul>
		</div>
	</header>
</template>

<script>
export default {
	name: "Navigation5",
	data() {
		return {
			mobile: null,
			mobileNav: null,
			windowWidth: null,
		};
	},
	created() {
		window.addEventListener("resize", this.checkScreenSize);
		this.checkScreenSize();
	},
	methods: {
		toggleMobileNav() {
			this.mobileNav = !this.mobileNav;
		},
		checkScreenSize() {
			this.windowWidth = window.innerWidth;
			if (this.windowWidth <= 1000) {
				this.mobile = true;
				return;
			}
			this.mobile = false;
			this.mobileNav = false;
			return;
		},
	},
};
</script>
<style lang="scss" scoped>
@import "/src/scss/variables";
$hamburger-color: rgb(255, 115, 0);
$navigation-bg: rgb(253, 226, 208);
$links-color: rgba(0, 0, 0, 0.726);

header {
	background: transparent;
	.navigation {
		width: 80%;
		padding: 5rem 0;
		margin: auto;
		display: flex;
		justify-content: flex-start;
		align-items: center;
		gap: 8rem;
		@media screen and (max-width: 1000px) {
			display: flex;
			justify-content: space-between;
		}
		@media screen and (max-width: 400px) {
			gap: 0rem;
		}
		img {
			position: relative;
			width: 8rem;
			height: 2rem;
			z-index: 2;
		}
		&__logo {
			a {
				outline: noen;
			}
		}
		&__links {
			ul {
				display: flex;
				li {
					list-style: none;
					&:not(:last-child) {
						margin-right: 5rem;
					}
				}
				a {
					outline: none;
					font-size: 1.7rem;
					text-decoration: none;
					color: $white;
					position: relative;
					&:focus {
						border: 2px dotted $black;
					}
					&:hover {
						transition: 0.2s ease-in-out;
						&:after {
							opacity: 1;
							background: $white;
							transition: all 0.4s ease-in-out;
							transform: scaleX(1);
						}
					}
					&:after {
						content: "";
						position: absolute;
						width: 120%;
						height: 3px;
						top: 32px;
						left: -10%;
						right: 10%;
						opacity: 0;
						transform: scaleX(0);
					}
				}
			}
		}
		&__hamburger {
			position: relative;
			cursor: pointer;
			z-index: 2;
			.line {
				fill: none;
				stroke: $white;
				stroke-width: 6;
				transition: stroke-dasharray 600ms cubic-bezier(0.4, 0, 0.2, 1),
					stroke-dashoffset 600ms cubic-bezier(0.4, 0, 0.2, 1);
				&:nth-child(1) {
					stroke-dasharray: 60 207;
					stroke-width: 9;
				}
				&:nth-child(2) {
					stroke-dasharray: 60 60;
					stroke-width: 9;
				}
				&:nth-child(3) {
					stroke-dasharray: 60 207;
					stroke-width: 9;
				}
			}
			.active {
				&:nth-child(1) {
					stroke-dasharray: 90 207;
					stroke-dashoffset: -134;
					stroke-width: 9;
				}
				&:nth-child(2) {
					stroke-dasharray: 1 60;
					stroke-dashoffset: -30;
					stroke-width: 9;
				}
				&:nth-child(3) {
					stroke-dasharray: 90 207;
					stroke-dashoffset: -134;
					stroke-width: 9;
				}
			}
		}
	}
}
.mobile__links {
	position: fixed;
	top: 0;
	left: 0;
	z-index: 0;
	width: 100vw;
	min-height: 100vh;
	padding-top: 15rem;
	background-color: black;
	display: block !important;
	visibility: hidden;
	opacity: 0;
	transition: all 0.6s ease-in-out;

	li {
		margin-bottom: 4rem;
		text-align: center;
	}
	a {
		text-decoration: none;
		color: $white;
		font-size: 1.8rem;
		outline: none;
		&:focus {
			border: 2px dotted $white;
		}
	}
}
.active {
	z-index: 1;
	visibility: visible;
	opacity: 1;
	transition: all 0.6s linear;
}
</style>
