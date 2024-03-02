<script lang="ts">
	import Layout from './components/layout/Layout.svelte'
	import Home from './components/screens/home/Home.svelte'
</script>

<Layout>
	<main class="overflow-hidden" slot="main"><Home /></main>
</Layout>
