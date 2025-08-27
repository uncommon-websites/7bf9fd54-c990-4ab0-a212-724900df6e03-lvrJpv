<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();
</script>

<section class={`bg-[#1F1D1A] py-16 sm:py-24 lg:py-32 ${className}`}>
	<div class="mx-auto max-w-[1728px] px-7 md:px-8 lg:px-9 xl:px-10">
		<div class="flex flex-col gap-16 md:gap-18 lg:gap-20 xl:gap-24">
			<div class="mx-auto max-w-lg text-center lg:max-w-none">
				<h2 class="text-balance text-3xl font-medium text-white md:text-4xl">
					A Platform Built for the Factory Floor
				</h2>
			</div>
			<div class="mx-auto lg:max-w-5xl xl:max-w-6xl">
				<div
					class="grid grid-cols-1 gap-y-16 md:grid-cols-2 md:gap-x-8 md:gap-y-16 lg:grid-cols-4 lg:gap-x-18 xl:gap-x-20"
				>
					<article
						class="flex flex-col items-center gap-4 text-center md:items-start md:gap-5 md:text-start"
					>
						<svg
							width="36"
							height="36"
							viewBox="0 0 36 36"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							class="h-9 w-9"
						>
							<path
								d="M18 33C18 33 30.375 27.3 30.375 18V7.8L18 3L5.625 7.8V18C5.625 27.3 18 33 18 33Z"
								stroke="#FDFDFC"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							></path>
						</svg>
						<div class="flex flex-col gap-2.5">
							<h3 class="text-lg font-semibold text-white">Enterprise-Grade Security</h3>
							<p class="text-base font-normal text-gray-400">
								Robust, industry-standard protection. Your proprietary process data is encrypted and
								secure.
							</p>
						</div>
					</article>
					<article
						class="flex flex-col items-center gap-4 text-center md:items-start md:gap-5 md:text-start"
					>
						<svg
							width="37"
							height="36"
							viewBox="0 0 37 36"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							class="h-9 w-9"
						>
							<path
								d="M21.125 3H12.375L17 15H8.25L14.125 33L20 21H28.75L21.125 3Z"
								stroke="#FDFDFC"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							></path>
						</svg>
						<div class="flex flex-col gap-2.5">
							<h3 class="text-lg font-semibold text-white">Automated Visual Guides</h3>
							<p class="text-base font-normal text-gray-400">
								Our AI transforms screen recordings into clear, step-by-step instructions with
								screenshots and annotations.
							</p>
						</div>
					</article>
					<article
						class="flex flex-col items-center gap-4 text-center md:items-start md:gap-5 md:text-start"
					>
						<svg
							width="37"
							height="36"
							viewBox="0 0 37 36"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							class="h-9 w-9"
						>
							<path
								d="M18.5 3V9M15.5 6H21.5M27.5 13.5C29.433 13.5 31.183 14.467 32.316 15.9C33.45 17.333 33.867 19.05 33.5 20.7C33.133 22.35 32.05 23.767 30.5 24.6C28.95 25.433 27.083 25.583 25.25 25.1L18.5 23.25L11.75 25.1C9.91667 25.583 8.05 25.433 6.5 24.6C4.95 23.767 3.86667 22.35 3.5 20.7C3.13333 19.05 3.55 17.333 4.68333 15.9C5.81667 14.467 7.56667 13.5 9.5 13.5H27.5ZM18.5 23.25V33"
								stroke="#FDFDFC"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							></path>
						</svg>
						<div class="flex flex-col gap-2.5">
							<h3 class="text-lg font-semibold text-white">Manufacturing-Specific Vision</h3>
							<p class="text-base font-normal text-gray-400">
								Custom computer vision models trained to understand the unique interfaces of ERPs and
								manufacturing software.
							</p>
						</div>
					</article>
					<article
						class="flex flex-col items-center gap-4 text-center md:items-start md:gap-5 md:text-start"
					>
						<svg
							width="36"
							height="37"
							viewBox="0 0 36 37"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							class="h-9 w-9"
						>
							<path
								d="M18 33.5C26.2843 33.5 33 27.5196 33 20C33 12.4804 26.2843 6.5 18 6.5C9.71573 6.5 3 12.4804 3 20C3 23.1333 4.416 25.9167 6.6 27.85C7.2 28.35 7.58333 29.1333 7.41667 29.95C7.16667 31.1333 6.58333 32.2 5.75 33.05C6.95 33.3333 8.21667 33.5 9.5 33.5H18Z"
								stroke="#FDFDFC"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							></path>
						</svg>
						<div class="flex flex-col gap-2.5">
							<h3 class="text-lg font-semibold text-white">Instant Search & Access</h3>
							<p class="text-base font-normal text-gray-400">
								A centralized, searchable knowledge base means your team can find the right answer in
								seconds, not hours.
							</p>
						</div>
					</article>
				</div>
			</div>
		</div>
	</div>
</section>