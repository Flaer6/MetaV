<script lang="ts">
	import Container from '../../../layout/Container.svelte'
	import VideoSlider from '../../../ui/sliders/videos/VideoSlider.svelte'
</script>

<section class="wrapper" id="resource">
	<Container>
		<div class="max-w-[562px] mx-auto text-center">
			<h2>Our Latest <span>Activity</span></h2>
			<p class="text-[#FFFFFFCC] pt-[16px]">
				Adipiscing at in tellus integer. Pellentesque massa placerat duis
				ultricies. Venenatis cras
			</p>
		</div>
	</Container>
	<VideoSlider />
</section>

<style lang="scss">
	.wrapper {
		@apply relative pt-[246px] pb-[229px] max-lg:pt-[200px] max-lg:pb-[190px] max-sm:pt-[100px] max-sm:pb-[90px];
		&::before {
			@apply content-[''] absolute top-[140px] -left-[200px] w-[300px] h-[300px] bg-[#d10eff] rounded-full blur-[190px];
		}
		&::after {
			@apply content-[''] absolute bottom-0 -right-[100px] w-[200px] h-[300px] bg-[#d10eff] rounded-full blur-[190px];
		}
	}
</style>
