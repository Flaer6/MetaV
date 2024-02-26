<script lang="ts">
	import { onMount } from 'svelte'
	import { cubicOut } from 'svelte/easing'
	import { tweened } from 'svelte/motion'
	import { states } from './states.data'

	const numbers = states.map(state => {
		return tweened(0, {
			duration: 1600,
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

<div class="pt-[40px] flex items-center gap-[68px]">
	{#each states as state, index}
		<dl class="">
			<dt class="text-[24px] font-medium font-Orbitron">
				{roundedNumbers[index]}K+
			</dt>
			<dd>{state.name}</dd>
		</dl>
	{/each}
</div>
