<script>
	import Section from '../../../layout/Section.svelte'
	import GetStarted from '../start/GetStarted.svelte'
	import State from '../state/State.svelte'
</script>

<Section className="wrapper relative">
	<div class="inner min-h-screen pt-[70px] flex items-center justify-between">
		<div class="max-w-[600px]">
			<h1 class="text-[45px] leading-[68px]">
				Explore the future of the <span>Metaverse</span>
			</h1>
			<p class="text-[20px] pt-[18px] max-w-[500px]">
				Let's explore and create your experience with metaverse.
			</p>
			<GetStarted />
			<State />
		</div>
		<div class="img-wrapper">
			<img class="" src="/top-img.png" alt="women" loading="lazy" />
		</div>
	</div>
</Section>

<style lang="scss">
	@import '../../../../assets/sass/mixins.scss';
	.img-wrapper {
		@apply relative;
		&::before {
			content: '';
			@apply w-[64px] h-[73px] absolute top-[130px] left-0;
			@include bg-img('/stars.svg', contain, center);
		}
		&::after {
			content: '';
			@apply w-[546px] h-[303px] absolute -bottom-[105px] -left-[80px] blur-[90px] bg-black;
		}
	}
	.inner {
		&::before {
			content: '';
			@apply absolute -top-[255px] left-[100px] w-[400px] h-[300px] bg-[#d10eff] blur-3xl rounded-full -z-[1];
		}
		&::after {
			content: '';
			@apply absolute top-[180px] -right-[150px] w-[200px] h-[500px] bg-[#d10eff] blur-3xl rounded-full -z-[1];
		}
	}
</style>
