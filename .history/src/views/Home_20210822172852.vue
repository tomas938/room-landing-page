<template>
	<header>
		<nav class="navigation">
			<div class="navigation__hamburger">
				<span></span>
				<span></span>
				<span></span>
			</div>
			<img src="../assets/logo.svg" alt="" />
		</nav>
	</header>
</template>

<script>
export default {
	name: "Home",
	components: {},
};
</script>
<style scoped lang="scss">
@import "/src/scss/variables";
header {
	width: 100%;
	background-color: red;
}
.navigation {
	height: 10rem;
	background-color: transparent;
	width: 100%;
	display: flex;
	align-items: flex-end;
	&__hamburger {
		// margin-left: 4rem;
	}
	&__hamburger span {
		display: block;
		margin-top: 0.5rem;
		width: 3rem;
		height: 0.5rem;
		background-color: $white;
	}
}
img {
	width: 8rem;
	height: 2rem;
}
</style>
