<script lang="ts">
	import Container from '../Container.svelte'
	import Logo from './Logo.svelte'
	import { aboutUs, contacts } from './links.data'
</script>

<footer class="footer">
	<Container>
		<div class="inner">
			<div class="max-w-[530px]">
				<Logo />
				<p class="text-[#FFFFFFCC] pt-[23px]">
					Adipiscing at in tellus integer. Pellentesque massa placerat duis
					ultricies lacus. Nisi porta lorem mollis aliquam ut porttitor
				</p>
			</div>
			<div class="">
				<ul>
					<li class="title">About Us</li>
					<ul class="flex flex-col gap-[8px]">
						{#each aboutUs as item}
							<li>
								<a href={item.link}>{item.name}</a>
							</li>
						{/each}
					</ul>
				</ul>
			</div>
			<div class="">
				<ul>
					<li class="title">Contact</li>
					<ul class="flex items-center gap-[21px] pb-[24px]">
						{#each contacts as contact}
							<li>
								<a href={contact.link}>
									<img src={contact.img} alt="img" />
								</a>
							</li>
						{/each}
					</ul>
					<li class="text-[16px]">2022 © MetaV.com All right reserved.</li>
				</ul>
			</div>
		</div>
	</Container>
</footer>

<style lang="scss">
	.footer {
		@apply bg-[#090823] pt-[104px] pb-[120px] max-lg:pt-[65px] max-lg:pb-[50px];
	}
	.inner {
		@apply flex justify-between items-start gap-3 max-lg:flex-wrap max-lg:items-end;
	}
	.title {
		@apply font-Orbitron text-[20px] font-bold mb-[21px];
	}
</style>
