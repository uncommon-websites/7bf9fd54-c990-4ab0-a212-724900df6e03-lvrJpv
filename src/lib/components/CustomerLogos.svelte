<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// Types
	type Logo = {
		src: string;
		alt: string;
	};

	// State
	// The logo data is static, so we use $state.raw for performance.
	// The original HTML showed 38 logos, which is a duplicated list for the infinite scroll effect.
	// We define a base list of 19 logos and then duplicate it in the template.
	const logos: Logo[] = $state.raw(
		Array(19).fill({
			src: 'https://www.ledr.com/colours/white.jpg',
			alt: 'Customer Logo'
		})
	);
</script>

<style>
	@keyframes scroll {
		to {
			/* This transformation creates the infinite scroll effect.
			 * It moves the container left by exactly half of its width.
			 * The '-1.5rem' accounts for the 'mx-6' margin on the list items,
			 * ensuring the animation is perfectly seamless. */
			transform: translate(calc(-50% - 1.5rem));
		}
	}
</style>

<section id="customers" class="overflow-hidden bg-gray-950 py-16 sm:py-24 lg:py-32 {className}">
	<div class="mx-auto max-w-[1728px] px-7 md:px-8 lg:px-9 xl:px-10">
		<div class="flex flex-col items-center gap-y-8">
			<h2 class="text-balance text-center text-3xl font-medium text-white sm:text-4xl">
				Trusted by Leading Manufacturers
			</h2>
			<div class="relative flex w-full flex-col items-center gap-y-6">
				<!-- Left-side fade effect to hide the edge of the scrolling container -->
				<div
					class="pointer-events-none absolute top-0 left-0 z-10 h-[78px] w-[20vw] bg-gradient-to-r from-gray-950 to-transparent md:w-[10vw]"
				></div>

				<div class="w-full max-w-[2000px] overflow-hidden">
					<!-- The 'animate-[scroll...]' class uses the custom @keyframes defined in the <style> tag -->
					<ul class="flex w-max animate-[scroll_60s_linear_infinite] flex-nowrap">
						<!-- The logo list is rendered twice to create a continuous, seamless loop -->
						{#each [...logos, ...logos] as logo, i}
							<li class="mx-6 h-[78px] w-fit flex-none">
								<img {src} alt={logo.alt} loading="lazy" class="h-full w-auto" />
							</li>
						{/each}
					</ul>
				</div>

				<!-- Right-side fade effect -->
				<div
					class="pointer-events-none absolute top-0 right-0 z-10 h-[78px] w-[20vw] bg-gradient-to-l from-gray-950 to-transparent md:w-[10vw]"
				></div>

				<a
					href="#"
					class="flex items-center gap-x-1 font-medium text-gray-500 transition-colors duration-300 ease-out hover:text-white active:text-gray-200"
				>
					<p>View Customer Stories</p>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 20 20"
						fill="currentColor"
						class="h-5 w-5"
						aria-hidden="true"
					>
						<path
							fill-rule="evenodd"
							d="M2 10a.75.75 0 0 1 .75-.75h12.59l-2.1-1.95a.75.75 0 1 1 1.02-1.1l3.5 3.25a.75.75 0 0 1 0 1.1l-3.5 3.25a.75.75 0 1 1-1.02-1.1l2.1-1.95H2.75A.75.75 0 0 1 2 10Z"
							clip-rule="evenodd"
						></path>
					</svg>
				</a>
			</div>
		</div>
	</div>
</section>