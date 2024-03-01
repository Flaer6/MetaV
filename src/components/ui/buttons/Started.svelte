<script lang="ts">
	export let className: string = ''
</script>

<a href="/" class="{className} started">
	<slot />
</a>

<style lang="scss">
	@import '../../../assets/sass/vars.scss';
	.started {
		@apply relative inline-block rounded-[5px] text-[20px] font-medium max-md:text-[18px] max-[455px]:text-[16px];
		background: $neon;
		transition: all 0.3s ease;
		&:hover {
			// background: $main-bg;
			@apply shadow-inner shadow-zinc-950;
		}
		&::before {
			content: '';
			@apply absolute -top-[1px] -bottom-[1px] -left-[1px] -right-[1px] rounded-[5px] -z-[1];
			background: $neon;
		}
	}
</style>
