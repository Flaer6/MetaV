<script>
	import Section from '../../../layout/Section.svelte'
	import GetStarted from '../start/GetStarted.svelte'
	import State from '../state/State.svelte'
</script>

<Section className="wrapper relative overflow-hidden">
	<div class="inner">
		<div class="max-w-[600px] max-lg:max-w-[460px]">
			<h1
				class="text-[45px] leading-[68px] max-md:text-[40px] max-md:leading-[55px] relative z-[1] max-[455px]:text-[30px] max-[455px]:leading-[40px]"
			>
				Explore the future of the <span>Metaverse</span>
			</h1>
			<p
				class="text-[20px] pt-[18px] max-w-[500px] max-md:text-[18px] max-md:pt-[15px] max-[455px]:pt-[35px] max-[455px]:text-[16px] max-[455px]:leading-[20px]"
			>
				Let's explore and create your experience with metaverse.
			</p>
			<GetStarted />
			<div class="max-sm:hidden">
				<State />
			</div>
		</div>
		<div class="img-wrapper">
			<img class="" src="/top-img.png" alt="women" loading="lazy" />
			<div class="sm:hidden">
				<State />
			</div>
		</div>
	</div>
</Section>

<style lang="scss">
	@import '../../../../assets/sass/mixins.scss';
	.img-wrapper {
		@apply relative max-md:max-w-[285px];
		&::before {
			content: '';
			@apply w-[64px] h-[73px] absolute top-[130px] left-0 max-sm:content-none;
			@include bg-img('/stars.svg', contain, center);
			animation: imgAnimate 2.1s linear infinite alternate;
		}
		&::after {
			content: '';
			@apply w-[546px] h-[303px] absolute -bottom-[105px] -left-[80px] blur-[90px] bg-black max-sm:h-[210px];
		}
		img {
			animation: imgAnimate 1.5s ease;
		}
	}
	.inner {
		@apply min-h-screen pt-[70px] flex items-center justify-between max-md:flex-col-reverse max-md:justify-stretch max-md:gap-[25px] max-[455px]:pt-[40px] max-sm:justify-center max-sm:items-center max-sm:text-center max-sm:pt-0 relative;
		&::before {
			content: '';
			@apply absolute -top-[255px] left-[100px] w-[400px] h-[300px] bg-[#d10eff] blur-3xl rounded-full -z-[1];
		}
		&::after {
			content: '';
			@apply absolute top-[180px] -right-[150px] w-[200px] h-[500px] bg-[#d10eff] blur-3xl rounded-full -z-[1];
		}
	}
	@keyframes imgAnimate {
		0% {
			opacity: 0.3;
			transform: translateY(15px);
		}
		100% {
			opacity: 1;
		}
	}
</style>
