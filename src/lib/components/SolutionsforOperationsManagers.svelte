<script lang="ts">
	// Types
	type Article = {
		title: string;
		description: string;
		imageUrl: string;
		imageAlt: string;
		imageOrder: 'first' | 'last';
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// Static data for the component's articles.
	// This keeps content local and avoids over-engineering with props for static text.
	const articles: Article[] = [
		{
			title: 'Standardize Work Processes',
			description:
				'Eliminate process variation and ensure every team member follows the correct procedure, every time.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Team standardizing workflows on a factory floor.',
			imageOrder: 'last'
		},
		{
			title: 'Reduce Training Time',
			description:
				'Slash onboarding time for new hires and cross-train existing staff with easy-to-follow visual instructions.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'A new hire being trained quickly using a tablet.',
			imageOrder: 'first'
		},
		{
			title: 'Minimize Production Delays',
			description:
				'Prevent costly errors and rework by giving your team instant access to the right information when they need it most.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Graph showing reduction in production delays.',
			imageOrder: 'last'
		},
		{
			title: 'Preserve Tribal Knowledge',
			description:
				'Capture the expertise of your most experienced employees before it walks out the door, creating a permanent knowledge asset.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'An experienced worker sharing knowledge with a younger colleague.',
			imageOrder: 'first'
		}
	];
</script>

<section class="bg-[#1F1D1A] py-16 sm:py-24 lg:py-32 {className}">
	<div class="mx-auto max-w-[1728px] px-7 md:px-8 lg:px-9 xl:px-10">
		<div class="mx-auto max-w-screen-xl">
			<div class="mb-12 text-center md:mb-16">
				<span class="text-xl text-gray-300 md:text-2xl">Built for Manufacturing Teams</span>
				<h2 class="mt-2 text-balance text-3xl font-medium text-white md:text-4xl lg:text-5xl">
					How Operations Managers Use Squint
				</h2>
			</div>
			<div class="flex flex-col gap-8 md:gap-12 lg:gap-16">
				{#each articles as article}
					<article class="flex flex-col overflow-hidden rounded-lg md:flex-row">
						<div
							class="relative w-full aspect-square md:w-1/2"
							class:md:order-last={article.imageOrder === 'last'}
						>
							<img class="h-full w-full object-cover" src={article.imageUrl} alt={article.imageAlt} />
						</div>
						<div
							class="flex w-full items-center justify-center bg-[#2C2A28] p-8 sm:p-12 md:w-1/2 md:p-16 lg:p-24"
						>
							<div class="flex max-w-xs flex-col gap-4 md:gap-5">
								<h3 class="text-balance text-3xl font-medium text-white lg:text-4xl">
									{article.title}
								</h3>
								<p class="text-gray-400">{article.description}</p>
								<a
									href="#"
									class="group mt-2 inline-flex items-center gap-2 font-medium text-gray-400 transition-colors hover:text-white"
								>
									Learn More
									<span aria-hidden="true" class="transition-transform group-hover:translate-x-1"
										>→</span
									>
								</a>
							</div>
						</div>
					</article>
				{/each}
			</div>
		</div>
	</div>
</section>