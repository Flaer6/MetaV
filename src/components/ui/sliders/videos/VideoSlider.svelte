<script lang="ts">
	import { onMount } from 'svelte'
	import Swiper from 'swiper'
	import { videos } from './video.data'

	let swiper
	onMount(() => {
		swiper = new Swiper('.mySwiper', {
			slidesPerView: 1.2,
			spaceBetween: 20,
			grabCursor: true,
			height: 650,
			breakpoints: {
				1180: {
					slidesPerView: 1.3,
				},
				748: {
					slidesPerView: 1.2,
					spaceBetween: 55,
				},
			},
		})
	})
</script>

<div class="mySwiper">
	<div class="swiper-wrapper">
		{#each videos as video}
			<div class="swiper-slide">
				<a href={video.link} class="video" title={video.name}>
					<img src={video.img} alt="img" />
				</a>
			</div>
		{/each}
	</div>
</div>

<style lang="scss">
	@import '../../../../assets/sass/mixins.scss';
	.mySwiper {
		@apply max-w-[2000px] mx-auto pt-[55px] px-[15px];
	}
	.video {
		@apply relative;
		&::before {
			@apply content-[''] absolute top-[50%] left-[50%] w-[120px] h-[120px] -translate-x-[50%] -translate-y-[50%] max-[1180px]:w-[100px] max-[1180px]:h-[100px] max-lg:w-[80px] max-lg:h-[80px] max-sm:w-[60px] max-sm:h-[60px];
			@include bg-img('/play.svg', contain, center);
		}
		&::after {
			@apply content-[attr(title)] absolute bottom-[50px] left-[50px] text-[45px] font-Orbitron font-semibold leading-[56px] max-[1180px]:bottom-[20px] max-[1180px]:left-[20px] max-[1180px]:text-[35px] max-lg:left-[10px] max-lg:bottom-[10px] max-lg:text-[30px] max-lg:leading-[30px] max-sm:text-[20px] max-[430px]:text-[18px] max-[430px]:leading-[18px];
		}
	}
</style>
