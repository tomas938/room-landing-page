<template>
	<nav class="navigation">
		<div class="navigation__hamburger"></div>
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
nav {
	height: 10rem;
	background-color: red;
}
img {
	width: 5rem;
	height: 5rem;
}
</style>
