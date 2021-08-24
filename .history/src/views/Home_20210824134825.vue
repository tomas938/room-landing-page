<template>
	<preloader></preloader>
	<Header></Header>
	<About></About>
</template>

<script>
import Header from "../components/Header";
import About from "../components/About";
import preloader from "../components/About";
export default {
	components: {
		Header,
		About,
		preloader,
	},
};
</script>
