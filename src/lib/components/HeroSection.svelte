<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// Functions
	/**
	 * Handles the click event on the play video button.
	 * In a real application, this would trigger a video player modal or inline playback.
	 * @param e - The mouse event.
	 */
	function handlePlayVideo(e: MouseEvent) {
		e.preventDefault();
		console.log('Play video action triggered.');
	}
</script>

<section
	id="hero"
	class="bg-[#1F1D1A] pt-24 pb-16 text-gray-200 sm:pb-24 lg:pb-32 {className}"
>
	<div class="mx-auto max-w-[1728px] px-7 md:px-8 lg:px-9 xl:px-10">
		<div class="flex flex-col items-center gap-8">
			<div class="flex flex-col items-center gap-4 text-center">
				<div>
					<h1
						class="text-balance text-6xl font-bold leading-tight text-gray-50 md:text-7xl lg:text-8xl"
					>
						Turn Expertise into
					</h1>
					<h1
						class="text-balance text-6xl font-bold leading-tight text-gray-50 md:text-7xl lg:text-8xl"
					>
						Instructions. Instantly.
					</h1>
				</div>
				<p class="mx-auto max-w-xl text-balance text-lg font-normal text-gray-300">
					Squint's computer vision automatically captures your team's tribal knowledge, creating
					visual, searchable work instructions to standardize processes and slash training time.
				</p>
			</div>
			<a
				href="#"
				class="flex h-12 cursor-pointer items-center justify-center whitespace-nowrap rounded-sm bg-gray-100 px-5 text-base font-medium text-black transition-colors duration-300 hover:bg-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-400 focus:ring-offset-2 focus:ring-offset-[#1F1D1A] active:bg-gray-400"
			>
				Request a Demo
			</a>
			<div class="mt-8 w-full md:mt-16">
				<div class="group relative aspect-video w-full cursor-pointer overflow-hidden rounded-sm">
					<div class="absolute inset-0 bg-black">
						<img
							alt="Video showing Squint capturing a manufacturing process"
							src="https://www.ledr.com/colours/white.jpg"
							class="h-full w-full object-cover"
						/>
					</div>
					<button
						onclick={handlePlayVideo}
						aria-label="Play Video"
						class="absolute left-1/2 top-1/2 z-10 -translate-x-1/2 -translate-y-1/2 scale-75 backdrop-blur-sm transition-opacity duration-500 md:scale-100"
					>
						<div
							class="flex h-14 w-14 items-center overflow-hidden rounded-sm bg-gray-800/50 transition-all duration-500 ease-in-out group-hover:w-44 group-hover:bg-gray-800/70 md:h-[72px] md:w-[72px]"
						>
							<div
								class="flex items-center gap-2 pl-4 transition-transform duration-500 ease-in-out md:pl-5"
							>
								<svg
									class="h-6 w-6 flex-shrink-0 text-gray-200"
									fill="currentColor"
									viewBox="0 0 24 24"
									aria-hidden="true"
								>
									<path d="M7.5 5.25L17.25 12L7.5 18.75V5.25Z" />
								</svg>
								<span
									class="whitespace-nowrap text-base text-gray-100 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
								>
									Watch Video
								</span>
							</div>
						</div>
					</button>
				</div>
			</div>
		</div>
	</div>
</section>