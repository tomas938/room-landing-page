<template>
	<Preloader></Preloader>
	<Header></Header>
	<About></About>
</template>

<script>
import Header from "../components/Header";
import About from "../components/About";
import Preloader from "../components/About";
export default {
	components: {
		Header,
		About,
		Preloader,
	},
};
</script>
