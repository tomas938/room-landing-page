<template>
	<router-view />
</template>

<style lang="scss">
@import "./scss/variables";
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
html {
	font-size: 82.5%;
	@media only screen and (min-width: 600px) {
		font-size: 62.5%;
	}
}
body {
	font-size: 1.2rem;
	font-family: $font-primary;
}
section {
	padding: 8rem 2rem;
}
</style>
