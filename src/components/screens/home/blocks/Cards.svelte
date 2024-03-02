<script lang="ts">
	import type { ObserverEventDetails } from 'svelte-inview'
	import { inview } from 'svelte-inview'
	import Explore from '../../../ui/buttons/Explore.svelte'
	import Started from '../../../ui/buttons/Started.svelte'
	import { cardsList } from './cards.data'

	let blockStates = Array(cardsList.length).fill(false)

	const handleChange =
		(index: number) =>
		({ detail }: CustomEvent<ObserverEventDetails>) => {
			blockStates[index] = detail.inView
		}
</script>

<div
	class="pt-[87px] grid grid-cols-3 gap-x-[38px] gap-y-[36px] max-[1075px]:grid-cols-2 max-md:pt-[50px] max-md:grid-cols-1"
>
	{#each cardsList as card, index (index)}
		<div
			class="block"
			use:inview={{ unobserveOnEnter: true, threshold: 0.1 }}
			on:inview_change={handleChange(index)}
			class:view={blockStates[index]}
		>
			<img class="w-full" src={card.img} alt="Card" loading="lazy" />
			<h3 class="text-[20px] pt-[23px] pb-[8px]">{card.title}</h3>
			<p>{card.text}</p>
			<div class="pt-[22px] flex items-center gap-[13px]">
				<Started className="py-[12px] px-[14px]">Try now</Started>
				<Explore className="py-[12px] px-[14px]">Explore now</Explore>
			</div>
		</div>
	{/each}
</div>

<style lang="scss">
	.block {
		@apply px-[19px] pt-[18px] pb-[37px] bg-[#090823] rounded-tr-[35px] rounded-bl-[35px] z-[1] opacity-10 scale-50;
		transition: all 0.7s ease;
		&.view {
			@apply opacity-100 scale-100;
		}
	}
</style>
