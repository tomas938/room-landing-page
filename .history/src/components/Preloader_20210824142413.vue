<template>
	<transition name="fade">
		<div v-if="show" class="preloader">
			<div class="logo"></div>
			<p>Discover the design</p>
			<div class="circles">
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
			</div>
		</div>
	</transition>
</template>

<script>
export default {
	name: "preloader",
	data() {
		return {
			show: true,
		};
	},
	mounted() {
		if (this.show) this.showToggle();
	},
	methods: {
		showToggle() {
			setTimeout(() => {
				this.show = false;
			}, 1000);
		},
	},
};
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
	background-color: rgb(0, 0, 0);
	z-index: 9999;
	// .logo {
	// 	width: 12.5rem;
	// 	height: 12.5rem;
	// 	background: rgb(59, 235, 103);
	// 	background-repeat: no-repeat;
	// }
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
			margin: 0.75rem;
			background-color: rgb(59, 235, 103);
			border-radius: 50%;
			animation-name: scaleIn;
			animation-duration: 0.7s;
			transform: scale(0);
			&:nth-child(1) {
				animation-delay: 0s;
			}
			&:nth-child(2) {
				animation-delay: 0.05s;
			}
			&:nth-child(3) {
				animation-delay: 0.1s;
			}
			&:nth-child(4) {
				animation-delay: 0.15s;
			}
			&:nth-child(5) {
				animation-delay: 0.2s;
			}
		}
	}
}
.fade-enter-active,
.fade-leave-active {
	transition: opacity 0.8s;
}
.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
@keyframes scaleOut {
	0% {
		transform: scale(1);
	}
	100% {
		transform: scale(0);
	}
}
@keyframes scaleIn {
	0% {
		transform: scale(0);
	}
	100% {
		transform: scale(1);
	}
}
</style>
