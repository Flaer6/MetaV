<script lang="ts">
	import Container from '../../../layout/Container.svelte'
	import Cards from '../blocks/Cards.svelte'
</script>

<section class="wrapper" id="pricing">
	<Container>
		<div class="pt-[165px] max-md:pt-[110px]">
			<div class="text-center max-w-[602px] mx-auto">
				<h2 class="pb-[16px]">How does the <span>Metaverse work</span></h2>
				<p class="text-[#FFFFFFCC]">
					Adipiscing at in tellus integer. Pellentesque massa placerat duis
					ultricies. Venenatis cras
				</p>
			</div>
			<Cards />
		</div>
	</Container>
</section>

<style lang="scss">
	.wrapper {
		@apply relative;
		&::after {
			@apply content-[''] absolute top-0 -right-[300px] w-[350px] h-[500px] bg-[#d10eff] rounded-full blur-[180px] -z-[1];
		}
	}
</style>
