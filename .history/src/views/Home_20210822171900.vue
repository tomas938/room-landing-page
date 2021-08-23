<template>
	<nav class="navigation">
		<div class="navigation__hamburger">
			<span></span>
			<span></span>
			<span></span>
		</div>
		<img src="../assets/logo.svg" alt="" />
	</nav>
</template>

<script>
export default {
	name: "Home",
	components: {},
};
</script>
<style scoped lang="scss">
@import "/src/scss/variables";
.navigation {
	height: 10rem;
	background-color: red;
	display: flex;
	&__hamburger span {
		display: block;
		margin-top: 0.5rem;
		width: 3rem;
		height: 0.5rem;
		background-color: $white;
	}
}
img {
	width: 5rem;
	height: 5rem;
}
</style>
