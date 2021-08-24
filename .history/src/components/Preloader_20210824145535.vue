<template>
	<!-- <div v-if="show" class="preloader">
			<div class="logo"></div>
			<transition name="bade">
				<p>Discover the design</p>
			</transition>
			<div class="circles">
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
				<div class="circle"></div>
			</div>
		</div> -->
	<transition name="fade">
		<div class="preloader" v-if="show">
			<svg>
				<g>
					<path d="M 50,100 A 1,1 0 0 1 50,0" />
				</g>
				<g>
					<path d="M 50,75 A 1,1 0 0 0 50,-25" />
				</g>
				<defs>
					<linearGradient id="gradient" x1="0%" y1="0%" x2="0%" y2="100%">
						<stop offset="0%" style="stop-color:#FF56A1;stop-opacity:1" />
						<stop offset="100%" style="stop-color:#FF9350;stop-opacity:1" />
					</linearGradient>
				</defs>
			</svg>
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
}
// 	p {
// 		color: #fff;
// 		font-size: 4rem;
// 		margin-bottom: 3rem;
// 	}
// 	.circles {
// 		display: flex;
// 		margin-top: 1rem;
// 		.circle {
// 			width: 1.5rem;
// 			height: 1.5rem;
// 			margin: 0.75rem;
// 			background-color: #fff;
// 			border-radius: 50%;
// 			animation-name: scaleIn;
// 			animation-duration: 0.7s;
// 			transform: scale(0);
// 			&:nth-child(1) {
// 				animation-delay: 0s;
// 			}
// 			&:nth-child(2) {
// 				animation-delay: 0.05s;
// 			}
// 			&:nth-child(3) {
// 				animation-delay: 0.1s;
// 			}
// 			&:nth-child(4) {
// 				animation-delay: 0.15s;
// 			}
// 			&:nth-child(5) {
// 				animation-delay: 0.2s;
// 			}
// 		}
// 	}
// }
.fade-enter-active,
.fade-leave-active {
	transition: opacity 0.8s;
}
.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
// .bade-enter-active,
// .bade-leave-active {
// 	transform: translateX(0px);
// 	transition: opacity 0.8s;
// }
// .bade-enter-from,
// .bade-leave-to {
// 	transform: translateX(-50px);
// }
// @keyframes scaleOut {
// 	0% {
// 		transform: scale(1);
// 	}
// 	100% {
// 		transform: scale(0);
// 	}
// }
// @keyframes scaleIn {
// 	0% {
// 		transform: scale(0);
// 	}
// 	100% {
// 		transform: scale(1);
// 	}
// }
$transition-duration: 2s;
$path-length: 157px; // Retrieved using SVG's getTotalLength()

html,
body {
	width: 100%;
	height: 100%;
}

body {
	display: flex;
	align-items: center;
	justify-content: center;
}

svg {
	overflow: visible;
	width: 100px;
	height: 150px;

	g {
		animation: slide $transition-duration linear infinite;

		&:nth-child(2) {
			animation-delay: $transition-duration / 4;

			path {
				animation-delay: $transition-duration / 4;
				stroke-dasharray: 0px $path-length + 1;
				stroke-dashoffset: 1px;
			}
		}
	}

	path {
		stroke: url(#gradient);
		stroke-width: 20px;
		stroke-linecap: round;
		fill: none;
		stroke-dasharray: 0 $path-length;
		stroke-dashoffset: 0;
		animation: escalade $transition-duration cubic-bezier(0.8, 0, 0.2, 1)
			infinite;
	}
}

@keyframes slide {
	0% {
		transform: translateY(-50px);
	}
	100% {
		transform: translateY(50px);
	}
}

@keyframes escalade {
	0% {
		stroke-dasharray: 0 $path-length;
		stroke-dashoffset: 0;
	}
	50% {
		stroke-dasharray: $path-length - 1 $path-length;
		stroke-dashoffset: 0;
	}
	100% {
		stroke-dasharray: $path-length - 1 $path-length;
		stroke-dashoffset: -($path-length - 1);
	}
}
</style>
