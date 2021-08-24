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
    .circles {

    display: flex;
		margin-top: 1rem;
		.circle {

			width: 1.5rem;
			height: 1.5rem;
			margin: .75rem;
			background-color: red;
			border-radius: 50%;
			animation-name: scaleIn;
			animation-duration: .7s;
			transform: scale(0)
			&:nth-child(1)
				animation-delay: 0s;
			&:nth-child(2)
				animation-delay: .05s;
			&:nth-child(3)
				animation-delay: .1s;
			&:nth-child(4)
				animation-delay: .15s;
			&:nth-child(5)
				animation-delay: .2s;
        }
        }

}
// .fade-enter-active, .fade-leave-active {
//     transition:  opacity: 1s;
// }
</style>
