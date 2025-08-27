<script lang="ts">
	// Types
	type Testimonial = {
		quote: string;
		name: string;
		title: string;
		company: string;
		imageAlt: string;
		logoAlt: string;
		logoClasses: string;
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// State
	const testimonials: Testimonial[] = $state.raw([
		{
			quote:
				'“Squint has been a game-changer for our assembly line. We\'ve cut training time for new technicians by 60% and reduced assembly errors by over 40%. It paid for itself in the first quarter.”',
			name: 'John Miller',
			title: 'Operations Director',
			company: 'Apex Manufacturing',
			imageAlt: 'Abstract background image for Apex Manufacturing testimonial',
			logoAlt: 'Apex Manufacturing Logo',
			logoClasses: 'h-20 w-auto brightness-0 invert md:h-28'
		},
		{
			quote:
				'“We struggled with inconsistent processes across shifts. With Squint, we\'ve finally standardized our SOPs. The visual guides are foolproof, and our team adopted it instantly because it\'s so easy to use.”',
			name: 'Sarah Chen',
			title: 'Plant Manager',
			company: 'Precision Parts Inc.',
			imageAlt: 'Portrait of Sarah Chen',
			logoAlt: 'Precision Parts Inc. Logo',
			logoClasses: 'h-16 w-auto brightness-0 invert md:h-20'
		},
		{
			quote:
				'“I\'ve never seen a tool that captures tribal knowledge so effectively. We documented a complex machine setup in 15 minutes—a task that would have taken days of writing manuals. It\'s a must-have for any modern facility.”',
			name: 'David Rodriguez',
			title: 'Head of Continuous Improvement',
			company: 'Dynamic Fabricators',
			imageAlt: 'Portrait of David Rodriguez',
			logoAlt: 'Dynamic Fabricators Logo',
			logoClasses: 'h-16 w-auto brightness-0 invert md:h-20'
		},
		{
			quote:
				'“The biggest win for us is consistency. Now, whether it\'s a new hire or a veteran, everyone performs the task the same way. This has had a massive impact on our product quality and output.”',
			name: 'Emily Sato',
			title: 'Quality Assurance Manager',
			company: 'Gen-Tech',
			imageAlt: 'Portrait of Emily Sato',
			logoAlt: 'Gen-Tech Logo',
			logoClasses: 'h-16 w-auto brightness-0 invert md:h-20'
		},
		{
			quote:
				'“Our team was resistant to another software tool, but Squint\'s screen recording capture is brilliant. They just do their work, and the documentation is created automatically. Adoption was a non-issue.”',
			name: 'Mark O\'Connell',
			title: 'Operations Manager',
			company: 'Aero-Components',
			imageAlt: 'Portrait of Mark O\'Connell',
			logoAlt: 'Aero-Components Logo',
			logoClasses: 'h-16 w-auto brightness-0 invert md:h-20'
		}
	]);

	let activeIndex = $state(0);
	let carouselContainer: HTMLDivElement | undefined = $state(undefined);

	// Functions
	function goToSlide(index: number) {
		if (!carouselContainer) return;
		const slide = carouselContainer.children[index] as HTMLElement;
		if (slide) {
			slide.scrollIntoView({
				behavior: 'smooth',
				block: 'nearest',
				inline: 'start'
			});
		}
	}

	// Effects
	$effect(() => {
		if (!carouselContainer) return;

		const observer = new IntersectionObserver(
			(entries) => {
				for (const entry of entries) {
					if (entry.isIntersecting) {
						const index = Array.from(carouselContainer.children).indexOf(entry.target as HTMLElement);
						if (index > -1) {
							activeIndex = index;
						}
					}
				}
			},
			{
				root: carouselContainer,
				threshold: 0.7 // A slide is active when 70% is visible
			}
		);

		const slides = carouselContainer.children;
		for (const slide of slides) {
			observer.observe(slide);
		}

		return () => {
			for (const slide of slides) {
				observer.unobserve(slide);
			}
		};
	});
</script>

<section class={`bg-[#1F1D1A] py-16 sm:py-24 lg:py-32 ${className}`}>
	<div class="mx-auto max-w-[1728px] px-7 md:px-8 lg:px-9 xl:px-10">
		<div role="region" aria-roledescription="carousel" aria-label="Customer Testimonials">
			<div
				bind:this={carouselContainer}
				class="flex snap-x snap-mandatory overflow-x-auto pb-6 scrollbar-hide"
			>
				{#each testimonials as testimonial, i (testimonial.name)}
					<article class="w-full flex-shrink-0 snap-start md:w-[70%] md:pr-12">
						<a href="#" class="group block">
							<div class="relative overflow-hidden rounded-lg">
								<img
									src="https://www.ledr.com/colours/white.jpg"
									alt={testimonial.imageAlt}
									loading="lazy"
									class="aspect-[5/4] w-full object-cover transition-transform duration-500 group-hover:scale-105 md:aspect-video"
								/>
								<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
								<div class="absolute inset-0 flex items-center justify-center p-8">
									<img
										src="https://www.ledr.com/colours/white.jpg"
										alt={testimonial.logoAlt}
										class={testimonial.logoClasses}
									/>
								</div>
							</div>
							<div class="pt-8 md:flex md:items-start md:gap-8 md:px-6">
								<div class="flex-1">
									<blockquote class="text-lg text-[#F5F4F1] sm:text-xl">
										<p>{testimonial.quote}</p>
									</blockquote>
									<figcaption class="mt-6 text-base text-gray-400">
										<span class="font-medium text-gray-200">{testimonial.name}</span>, {testimonial.title},
										{testimonial.company}
									</figcaption>
								</div>
								<div class="mt-6 flex-shrink-0 md:mt-0">
									<span
										class="inline-flex items-center justify-center rounded-md bg-[#F5F4F1] px-5 py-3 text-base font-medium text-[#1F1D1A] transition-colors hover:bg-gray-300"
										>Read Case Study</span
									>
								</div>
							</div>
						</a>
					</article>
				{/each}
			</div>
			<div class="mt-8 flex justify-center gap-3" role="group" aria-label="Slide controls">
				{#each testimonials as _, i (i)}
					<button aria-label={`Go to slide ${i + 1}`} class="p-1" onclick={() => goToSlide(i)}>
						<span
							class="block h-2.5 w-2.5 rounded-full transition"
							class:bg-white={activeIndex === i}
							class:bg-gray-600={activeIndex !== i}
							class:hover:bg-gray-400={activeIndex !== i}
						></span>
					</button>
				{/each}
			</div>
		</div>
	</div>
</section>

<style>
	.scrollbar-hide::-webkit-scrollbar {
		display: none;
	}
	.scrollbar-hide {
		-ms-overflow-style: none; /* IE and Edge */
		scrollbar-width: none; /* Firefox */
	}
</style>