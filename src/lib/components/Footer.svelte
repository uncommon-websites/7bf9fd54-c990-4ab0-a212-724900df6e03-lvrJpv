<script lang="ts">
	/**
	 * Props for the Footer component.
	 * This component is largely static, so it only accepts a className prop
	 * for external styling overrides.
	 */
	let { className = '' }: { className?: string } = $props();
</script>

<footer class="bg-[#1F1D1A] text-white {className}">
	<div class="mx-auto max-w-[1920px] px-7 md:px-8 lg:px-9 xl:px-10">
		<section class="pb-7 md:pb-8 lg:pb-9 xl:pb-10">
			<div
				class="flex flex-col items-start gap-7 border-b border-gray-800 py-12 md:flex-row md:items-end md:justify-between md:py-24"
			>
				<h3 class="w-full max-w-2xl text-balance text-left text-3xl font-medium md:text-4xl lg:text-5xl">
					Ready to Standardize Your Operations?
				</h3>
				<a
					href="#"
					class="flex h-12 shrink-0 items-center justify-center whitespace-nowrap rounded-sm bg-[#F5F4F1] px-5 text-base font-medium leading-none text-[#1F1D1A] transition-colors duration-300 hover:bg-gray-400 active:bg-gray-300"
					>Request a Demo</a
				>
			</div>
		</section>
		<section>
			<div class="flex flex-col justify-between py-16 md:grid md:grid-cols-12 md:py-24">
				<div class="mb-16 md:col-span-3 md:mb-0">
					<a href="#" class="text-4xl font-bold text-white">Squint</a>
				</div>
				<div
					class="grid w-full grid-cols-2 gap-x-4 gap-y-12 md:col-span-6 md:col-start-7 md:grid-cols-4 md:gap-x-8"
				>
					<div class="flex flex-col gap-4">
						<small class="text-sm text-gray-500">Platform</small>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Capture<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Organize<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Search<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Integrations<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
					</div>
					<div class="flex flex-col gap-4">
						<small class="text-sm text-gray-500">Solutions</small>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Standardization<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Training<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Onboarding<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Quality Control<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
					</div>
					<div class="flex flex-col gap-4">
						<small class="text-sm text-gray-500">About</small>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Customers<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Security<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Company<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Blog<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Careers<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
					</div>
					<div class="flex flex-col gap-4">
						<small class="text-sm text-gray-500">Resources</small>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Legal<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Privacy Policy<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
						<a
							href="#"
							class="group flex text-pretty text-sm font-medium text-white transition-colors hover:text-gray-400"
							>Contact Us<span
								class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
								>→</span
							></a
						>
					</div>
				</div>
			</div>
			<div
				class="flex flex-col-reverse gap-6 pb-7 md:flex-row md:items-center md:justify-between md:pb-8 lg:pb-9 xl:pb-10"
			>
				<p class="text-balance text-sm text-gray-500">
					Copyright © 2025 Squint Inc. All rights reserved.
				</p>
				<div class="flex items-center gap-4">
					<a
						href="#"
						target="_blank"
						rel="noopener noreferrer"
						class="text-sm text-gray-500 transition-colors hover:text-white">X</a
					>
					<div class="h-3 w-px bg-gray-700"></div>
					<a
						href="#"
						target="_blank"
						rel="noopener noreferrer"
						class="text-sm text-gray-500 transition-colors hover:text-white">LinkedIn</a
					>
				</div>
			</div>
		</section>
	</div>
</footer>