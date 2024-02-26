<script>
	import Container from '../Container.svelte'
	import Navigation from './Navigation.svelte'
</script>

<header class="pt-[43px] absolute top-0 left-0 right-0 z-10">
	<Container>
		<div class="flex justify-between items-center">
			<div>
				<a href="/" class="font-Orbitron font-bold text-[22px]">MetaV</a>
			</div>
			<div class="">
				<Navigation />
			</div>
		</div>
	</Container>
</header>
