<template>
	<header>
		<nav class="navigation">
			<div class="navigation__hamburger">
				<span></span>
				<span></span>
				<span></span>
			</div>
			<div class="navigation__logo">
				<img src="../assets/logo.svg" alt="" />
			</div>
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
	background-image: url("../assets/mobile-image-hero-1.jpg");
	background-repeat: no-repeat;
}
.navigation {
	padding: 0 3rem;
	height: 8rem;
	background-color: transparent;
	display: flex;
	align-items: flex-end;
	&__hamburger span {
		display: block;
		margin-top: 0.5rem;
		width: 3rem;
		height: 0.5rem;
		background-color: $white;
	}
	&__logo {
		width: 100%;
		display: flex;
		justify-content: center;
	}
	img {
		width: 8rem;
		height: 2rem;
	}
}
</style>
