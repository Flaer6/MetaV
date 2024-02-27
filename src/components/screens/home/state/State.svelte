<script lang="ts">
	import { onMount } from 'svelte'
	import { cubicOut } from 'svelte/easing'
	import { tweened } from 'svelte/motion'
	import { states } from './states.data'

	const numbers = states.map(state => {
		return tweened(0, {
			duration: 1700,
			easing: cubicOut,
		})
	})

	onMount(() => {
		numbers.forEach((number, index) => {
			number.set(states[index].number)
		})
	})

	let roundedNumbers: number[] = []

	numbers.forEach((number, index) => {
		number.subscribe(value => {
			roundedNumbers[index] = Math.round(value)
		})
	})
</script>

<div
	class="pt-[40px] flex items-center gap-[68px] max-md:pt-[30px] max-[455px]:pt-[25px] max-[455px]:justify-between max-[455px]:gap-1"
>
	{#each states as state, index}
		<dl class="">
			<dt class="text-[24px] font-medium font-Orbitron max-md:text-[22px]">
				{roundedNumbers[index]}K+
			</dt>
			<dd>{state.name}</dd>
		</dl>
	{/each}
</div>
