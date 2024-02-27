<script>
	import { linksData } from './header.data'
</script>

<nav>
	<ul class="flex items-center gap-[50px] max-sm:hidden">
		{#each linksData as item}
			<li>
				<a
					class="text-[16px] transition-all hover:underline max-md:text-[15px]"
					href={item.link}>{item.name}</a
				>
			</li>
		{/each}
	</ul>
</nav>
