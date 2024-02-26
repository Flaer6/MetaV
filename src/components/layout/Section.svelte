<script lang="ts">
	import Container from './Container.svelte'
	export let className: string = ''
</script>

<section class={className}>
	<Container>
		<slot />
	</Container>
</section>
