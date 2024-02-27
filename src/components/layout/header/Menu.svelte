<script lang="ts">
	import { linksData } from './header.data'

	let isOpen: boolean = false
	const toggle = () => (isOpen = !isOpen)
</script>

<button on:click={toggle} class="btn">
	<span class="line {isOpen ? 'close' : ''}"></span>
	<span class="line {isOpen ? 'close' : ''}"></span>
	<span class="line {isOpen ? 'close' : ''}"></span>
	<span class="line {isOpen ? 'close' : ''}"></span>
</button>

<nav class="wrapperMenu {isOpen ? 'open' : ''}">
	<ul class="">
		{#each linksData as link}
			<li>
				<a href={link.link} class="link">{link.name}</a>
			</li>
		{/each}
	</ul>
</nav>

<style lang="scss">
	.btn {
		@apply sm:hidden w-[30px] h-[20px] relative z-10;
	}
	.line {
		@apply h-[1px] w-full bg-white absolute left-0 transition-all ease-out;
		&:nth-child(1) {
			top: 0;
		}
		&:nth-child(2) {
			top: 9px;
		}
		&:nth-child(3) {
			top: 9px;
		}
		&:nth-child(4) {
			bottom: 0;
		}
		&.close:nth-child(1) {
			transform: scale(0);
		}
		&.close:nth-child(2) {
			transform: rotate(-45deg);
		}
		&.close:nth-child(3) {
			transform: rotate(45deg);
		}
		&.close:nth-child(4) {
			transform: scale(0);
		}
	}
	.wrapperMenu {
		@apply min-h-screen min-w-[50%] absolute top-0 right-0 bg-neutral-950 text-right pt-[105px] origin-right scale-x-0 transition-all ease-out;
		&.open {
			@apply scale-x-100;
		}
	}
	.link {
		@apply py-[15px] border-b border-solid border-neutral-700 block pr-[15px] transition-all hover:bg-neutral-900;
	}
</style>
