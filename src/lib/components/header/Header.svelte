<script lang="ts">
	import { page } from '$app/stores';
	interface Page {
		title: string;
		path: string;
	}
	var pages: Page[] = [
		{ title: 'Home', path: '/' },
		{ path: '/about', title: 'About' },
		{ path: '/survey', title: 'Survey' },
		{ path: '/graph', title: 'Graph' }
	];

	$: currentPath = $page.url.pathname;
</script>

<!-- <header class="flex items-center justify-between px-10">
	<a href="/" class="p-5 font-extrabold transition-all hover:scale-125">AI in coding</a>
	<div>
		{#each pages as page}
			<a href={page.path} class="p-5 transition-all opacity-50 hover:opacity-100 ">{page.title}</a>
		{/each}
	</div>
</header> -->

<header
	class="backdrop:blur-sm  z-50 flex h-[4.5rem] items-center gap-2 px-2 md:px-10 left-0 right-0 top-0"
>
	<b class="text-gray-800 transition-all text-xl">
		<a href="/">LNG320 Artificial Intelligence</a></b
	>
	<ul class="flex-1 h-8">
		{#each pages as page}
			<li class="font-semibold text-gray-500 relative  h-full group">
				<a
					href={page.path}
					class="{page.path === currentPath
						? 'font-bold text-gray-900'
						: ''} p-5 h-full transition-all opacity-50 group-hover:opacity-100 "
					>{page.title}
				</a>
				<div
					class="{page.path === currentPath
						? 'w-10 '
						: 'w-0'} transition-all absolute bottom-0 left-0 group-hover:w-10  h-1 bg-gradient-to-r from-[#ff0080] to-[#7928ca]"
				/>
			</li>
		{/each}
	</ul>
	<a
		target="_blank"
		rel="external"
		class="p-4 font-semibold text-gray-500"
		href="https://github.com/FloatKasemtan/LNG-research-website/issues">Contact us</a
	>
</header>

<style>
	header ul {
		display: flex;
		justify-content: center;
		gap: 1rem;
	}
</style>
