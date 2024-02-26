<script lang="ts">
	export let className: string = ''
</script>

<a href="/" class="{className} started">
	<slot />
</a>

<style lang="scss">
	@import '../../../assets/sass/vars.scss';
	.started {
		@apply relative rounded-[5px] text-[20px] font-medium box-border;
		background: $neon;
		transition: all 0.5s ease;
		&:hover {
			background: $main-bg;
		}
		&::before {
			content: '';
			@apply absolute -top-[1px] -bottom-[1px] -left-[1px] -right-[1px] rounded-[5px] -z-[1];
			background: $neon;
		}
	}
</style>
