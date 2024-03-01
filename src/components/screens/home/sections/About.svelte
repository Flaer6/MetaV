<script lang="ts">
	import type { ObserverEventDetails, Options } from 'svelte-inview'
	import { inview } from 'svelte-inview'
	import Container from '../../../layout/Container.svelte'
	import Started from '../../../ui/buttons/Started.svelte'

	let isInView: boolean
	const options: Options = {
		unobserveOnEnter: true,
		threshold: 0.5,
	}

	const handleChange = ({ detail }: CustomEvent<ObserverEventDetails>) => {
		isInView = detail.inView
	}
</script>

<section class="wrapper" use:inview={options} on:inview_change={handleChange}>
	<Container>
		<div class="inner">
			<div class="blockImg" class:animateLeft={isInView}>
				<img src="/about-img.png" alt="img" />
			</div>
			<div class="infoBlock" class:animateRight={isInView}>
				<h2>What is <span>Metaverse</span></h2>
				<p class="pt-[16px] pb-[52px] max-sm:pb-[35px]">
					Adipiscing at in tellus integer. Pellentesque massa placerat duis
					ultricies lacus. Nisi porta lorem mollis aliquam ut porttitor leo.
					Venenatis cras..
				</p>
				<Started className="py-[12px] px-[14px]">Know More</Started>
			</div>
		</div>
	</Container>
</section>

<style lang="scss">
	.wrapper {
		@apply relative;
		&::before {
			content: '';
			@apply absolute -top-[110px] -left-[250px] -z-[1] w-[500px] h-[500px] bg-[#d10eff] blur-3xl rounded-full opacity-40;
		}
	}
	.inner {
		@apply flex justify-between items-center gap-4 pt-[55px] max-md:flex-col max-md:gap-6 overflow-hidden max-sm:pt-0;
	}
	.blockImg {
		@apply -translate-x-full opacity-0;
		transition: all 1.5s ease;
		&.animateLeft {
			@apply translate-x-0 opacity-100;
		}
	}
	.infoBlock {
		@apply max-w-[525px] translate-x-full opacity-0;
		transition: all 1s ease;
		&.animateRight {
			@apply translate-x-0 opacity-100;
		}
	}
</style>
