<template>
	<section class="shop">
		<h1 class="active">{{ content[slide].heading }}</h1>
		<p>
			{{ content[slide].description }}
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
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
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
		max-width: 25rem;
		cursor: pointer;
		&:hover {
			a {
				color: $dark-gray;
				transition: color 0.3s ease-in-out;
			}
			svg path {
				fill: $dark-gray;
				transition: fill 0.3s ease-in-out;
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
}
</style>
