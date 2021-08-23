<template>
	<section class="shop">
		<h1 class="active">{{ content[slide].heading }}</h1>
		<p>
			{{ content[slide].description }}
		</p>
		<div class="shop__link" @click="log()">
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

<style lang="scss" scoped></style>
