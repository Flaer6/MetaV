<script>
	import { linksData } from './header.data'
</script>

<ul class="flex items-center gap-[50px]">
	{#each linksData as item}
		<li>
			<a class="text-[16px] transition-all hover:underline" href={item.link}
				>{item.name}</a
			>
		</li>
	{/each}
</ul>
