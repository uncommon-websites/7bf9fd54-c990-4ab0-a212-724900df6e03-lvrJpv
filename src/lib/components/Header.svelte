<script lang="ts">
	import { fade } from 'svelte/transition';

	// Props
	let { className = '' }: { className?: string } = $props();

	// --- State ---

	// Controls the visibility of the mobile navigation menu.
	let isMenuOpen = $state(false);

	// Tracks the currently active dropdown menu on desktop.
	type Dropdown = 'platform' | 'solutions' | null;
	let activeDropdown: Dropdown = $state(null);

	// --- Functions ---

	/**
	 * Toggles the mobile menu open or closed.
	 */
	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
		// When closing the menu, also close any active dropdowns.
		if (!isMenuOpen) {
			activeDropdown = null;
		}
	}

	/**
	 * Toggles a specific dropdown menu for the desktop navigation.
	 * @param dropdown The identifier of the dropdown to toggle.
	 */
	function toggleDropdown(dropdown: 'platform' | 'solutions') {
		activeDropdown = activeDropdown === dropdown ? null : dropdown;
	}

	// --- Effects ---

	/**
	 * A side effect to prevent the body from scrolling when the mobile menu is open.
	 * This improves user experience by locking the background content.
	 */
	$effect(() => {
		if (isMenuOpen) {
			document.body.style.overflow = 'hidden';
			// The cleanup function is returned and runs when the effect is re-evaluated or the component is unmounted.
			return () => {
				document.body.style.overflow = '';
			};
		}
	});
</script>

<header class="fixed top-0 z-50 w-full border-b border-gray-800/50 bg-[#1F1D1A] {className}">
	<div class="mx-auto flex h-24 max-w-[1920px] items-center px-7 md:px-8 lg:px-9 xl:px-10">
		<div class="relative flex h-full w-full items-center justify-between">
			<a
				href="#"
				aria-label="Home"
				class="text-xl font-bold text-white md:text-[32px] lg:text-4xl xl:text-[40px]"
			>
				Squint
			</a>

			<!-- Desktop Navigation -->
			<nav class="absolute left-1/2 hidden h-full -translate-x-1/2 items-center md:flex">
				<ul class="flex h-full items-center text-sm font-medium">
					<li class="h-full">
						<button
							onclick={() => toggleDropdown('platform')}
							aria-expanded={activeDropdown === 'platform'}
							class="flex h-full items-center gap-x-1.5 px-4 text-gray-300 transition-colors hover:text-white"
						>
							<span>Platform</span>
							<svg
								class="h-4 w-4 transition-transform {activeDropdown === 'platform' ? 'rotate-180' : ''}"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li class="h-full">
						<button
							onclick={() => toggleDropdown('solutions')}
							aria-expanded={activeDropdown === 'solutions'}
							class="flex h-full items-center gap-x-1.5 px-4 text-gray-300 transition-colors hover:text-white"
						>
							<span>Solutions</span>
							<svg
								class="h-4 w-4 transition-transform {activeDropdown === 'solutions' ? 'rotate-180' : ''}"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li class="h-full">
						<a href="#" class="flex h-full items-center px-4 text-gray-300 transition-colors hover:text-white"
							>Customers</a
						>
					</li>
					<li class="h-full">
						<a href="#" class="flex h-full items-center px-4 text-gray-300 transition-colors hover:text-white"
							>Security</a
						>
					</li>
					<li class="h-full">
						<a href="#" class="flex h-full items-center px-4 text-gray-300 transition-colors hover:text-white"
							>Company</a
						>
					</li>
				</ul>
			</nav>

			<div class="flex h-full items-center">
				<!-- Desktop CTAs -->
				<div class="hidden h-full items-center gap-x-1 md:flex">
					<a
						href="#"
						class="flex h-full items-center px-7 text-sm font-medium text-gray-300 transition-colors hover:text-white"
						>Login</a
					>
					<a
						href="#"
						class="flex h-8 items-center justify-center whitespace-nowrap rounded-sm bg-gray-100 px-3 text-sm font-medium text-gray-950 transition-colors hover:bg-gray-300"
					>
						Request a Demo
					</a>
				</div>

				<!-- Mobile Menu Toggle -->
				<button
					class="relative z-50 text-white md:hidden"
					type="button"
					aria-label={isMenuOpen ? 'Close menu' : 'Open menu'}
					aria-controls="mobile-menu"
					aria-expanded={isMenuOpen}
					onclick={toggleMenu}
				>
					{#if isMenuOpen}
						<!-- Close Icon (X) -->
						<svg
							class="h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
						</svg>
					{:else}
						<!-- Hamburger Icon -->
						<svg
							class="h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
							/>
						</svg>
					{/if}
				</button>
			</div>
		</div>
	</div>

	<!-- Mobile Navigation Panel -->
	{#if isMenuOpen}
		<div
			id="mobile-menu"
			class="absolute top-0 left-0 z-40 h-screen w-full bg-[#1F1D1A] pt-24 md:hidden"
			transition:fade={{ duration: 200 }}
		>
			<nav class="flex h-full flex-col justify-between p-8">
				<ul class="flex flex-col gap-y-2 text-lg font-medium">
					<li>
						<button
							class="flex w-full items-center justify-between py-2 text-gray-300 transition-colors hover:text-white"
						>
							<span>Platform</span>
							<svg
								class="h-5 w-5"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li>
						<button
							class="flex w-full items-center justify-between py-2 text-gray-300 transition-colors hover:text-white"
						>
							<span>Solutions</span>
							<svg
								class="h-5 w-5"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li>
						<a href="#" class="block py-2 text-gray-300 transition-colors hover:text-white">Customers</a>
					</li>
					<li>
						<a href="#" class="block py-2 text-gray-300 transition-colors hover:text-white">Security</a>
					</li>
					<li>
						<a href="#" class="block py-2 text-gray-300 transition-colors hover:text-white">Company</a>
					</li>
				</ul>
				<div class="flex flex-col gap-y-4 border-t border-gray-800 pt-6">
					<a
						href="#"
						class="flex h-12 items-center justify-center rounded-sm text-base font-medium text-gray-300 transition-colors hover:text-white"
						>Login</a
					>
					<a
						href="#"
						class="flex h-12 items-center justify-center whitespace-nowrap rounded-sm bg-gray-100 text-base font-medium text-gray-950 transition-colors hover:bg-gray-300"
					>
						Request a Demo
					</a>
				</div>
			</nav>
		</div>
	{/if}
</header>