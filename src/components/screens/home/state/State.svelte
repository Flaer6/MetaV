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

<div class="wrapper">
	{#each states as state, index}
		<dl class="state">
			<dt class="text-[24px] font-medium font-Orbitron max-md:text-[22px]">
				{roundedNumbers[index]}K+
			</dt>
			<dd>{state.name}</dd>
		</dl>
	{/each}
</div>

<style lang="scss">
	.wrapper {
		@apply pt-[40px] flex items-center gap-[68px] max-md:pt-[30px] max-[455px]:pt-[35px] max-[455px]:justify-between max-[455px]:gap-1;
		.state {
			@apply max-sm:absolute z-[1];
			&:nth-child(1) {
				animation: animate1 1.5s ease;
				@apply top-[60px] left-[0];
			}
			&:nth-child(2) {
				animation: animate2 1.5s ease;
				@apply -top-[50px] left-[150px];
			}
			&:nth-child(3) {
				animation: animate3 1.5s ease;
				@apply top-[15px] -right-[50px];
			}
		}
	}
	@keyframes animate1 {
		0% {
			transform: translateX(35px);
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes animate2 {
		0% {
			transform: translateY(-35px);
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes animate3 {
		0% {
			transform: translateX(-35px);
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
</style>
