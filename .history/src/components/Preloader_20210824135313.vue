<template>
	<transition name="fade">
		<div class="preloader">
			<p>preloader</p>
		</div>
	</transition>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.preloader {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	position: absolute;
	width: 100%;
	height: 100%;
	background-color: #fff;
	z-index: 9999;
	.logo {
		width: 12.5rem;
		height: 12.5rem;
		background: red;
		background-repeat: no-repeat;
	}
	p {
		font-size: 3rem;
		margin-top: 3rem;
	}
}
</style>
