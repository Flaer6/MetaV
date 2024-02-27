<script lang="ts">
	import Container from '../Container.svelte'
	import Menu from './Menu.svelte'
	import Navigation from './Navigation.svelte'
</script>

<header class="pt-[43px] absolute top-0 left-0 right-0 z-10 max-sm:pt-[20px]">
	<Container>
		<div class="flex justify-between items-center">
			<div>
				<a href="/" class="font-Orbitron font-bold text-[22px]">MetaV</a>
			</div>
			<div class="">
				<Navigation />
				<Menu />
			</div>
		</div>
	</Container>
</header>
