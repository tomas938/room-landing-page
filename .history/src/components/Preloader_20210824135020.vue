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
}
</style>
