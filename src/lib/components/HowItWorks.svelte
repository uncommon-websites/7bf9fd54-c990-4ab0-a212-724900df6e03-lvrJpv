<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// This component is purely presentational, so no state, derived values, or effects are needed.
	// All content is kept inline as per the requirements to maintain simplicity and clarity.
</script>

<section class="py-16 lg:py-32 bg-[#fdf6ee] {className}">
	<div
		class="mx-auto flex w-full max-w-7xl flex-col items-center justify-center gap-12 px-6 lg:gap-16"
	>
		<div
			class="relative flex w-full items-center justify-center overflow-hidden rounded-2xl bg-[#3e2407] px-6 py-20"
		>
			<img
				src="https://www.ledr.com/colours/black.jpg"
				alt="Abstract background"
				class="absolute inset-0 h-full w-full object-cover opacity-10"
			/>
			<div class="relative z-10 flex flex-col items-center justify-center gap-8">
				<svg
					width="37"
					height="26"
					viewBox="0 0 37 26"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
					class="h-[26px] w-[37px]"
					aria-hidden="true"
				>
					<path d="M18.5 0L12.3333 10.6667H24.6667L18.5 0Z" fill="white"></path>
					<path d="M11.5625 11.8542L5.39583 22.5208H17.7292L11.5625 11.8542Z" fill="white"></path>
					<path d="M25.4375 11.8542L19.2708 22.5208H31.6042L25.4375 11.8542Z" fill="white"></path>
				</svg>
				<div class="flex flex-col items-center gap-6">
					<h2
						class="text-center text-4xl font-normal leading-tight tracking-tight text-white md:text-5xl lg:text-[56px]"
					>
						Capture Knowledge in 3 Simple Steps
					</h2>
					<p class="max-w-md text-center text-[15px] font-normal leading-normal text-white">
						Overcome documentation resistance with a process so simple, your team will actually use
						it.
					</p>
				</div>
				<a
					href="#"
					class="inline-flex items-center justify-center rounded-xl bg-white px-4 py-3 text-[15px] font-medium text-[#2b180a] transition-colors hover:bg-gray-200"
				>
					Request a Demo
				</a>
			</div>
		</div>
		<div class="flex w-full flex-col gap-3 lg:flex-row">
			<div class="flex flex-1 flex-col gap-2 rounded-2xl bg-[#f7f0e8] p-5">
				<div class="flex items-center gap-2">
					<h4 class="text-xl font-normal leading-snug text-[#ff5c00]">01</h4>
					<h4 class="text-xl font-normal leading-snug text-[#2b180a]">Record Your Screen</h4>
				</div>
				<p class="text-[15px] font-normal leading-normal text-[#94877c]">
					Simply perform a task on your computer. Squint's recorder captures the process without
					interrupting your workflow.
				</p>
			</div>
			<div class="flex flex-1 flex-col gap-2 rounded-2xl bg-[#f7f0e8] p-5">
				<div class="flex items-center gap-2">
					<h4 class="text-xl font-normal leading-snug text-[#ff5c00]">02</h4>
					<h4 class="text-xl font-normal leading-snug text-[#2b180a]">AI Generates Instructions</h4>
				</div>
				<p class="text-[15px] font-normal leading-normal text-[#94877c]">
					Our computer vision analyzes the recording, automatically creating step-by-step visual
					guides with annotations.
				</p>
			</div>
			<div class="flex flex-1 flex-col gap-2 rounded-2xl bg-[#f7f0e8] p-5">
				<div class="flex items-center gap-2">
					<h4 class="text-xl font-normal leading-snug text-[#ff5c00]">03</h4>
					<h4 class="text-xl font-normal leading-snug text-[#2b180a]">Share with Your Team</h4>
				</div>
				<p class="text-[15px] font-normal leading-normal text-[#94877c]">
					Publish to a central, searchable knowledge base, giving everyone instant access to standard
					operating procedures.
				</p>
			</div>
		</div>
	</div>
</section>