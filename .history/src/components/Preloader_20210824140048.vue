<template>
	<transition name="fade">
		<div v-if="show" class="preloader">
			<div class="logo"></div>
			<p>Добро пожаловать!</p>
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
			}, 700);
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
			margin: 0.75rem;
			background-color: red;
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
	transition: opacity 1s;
}
@keyframes scaleOut {
	0% {
		transform: scale(1);
	}
	100% {
		transform: scale(0);
	}
}
</style>
