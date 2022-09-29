<script lang="ts">
	interface Page {
		title: string;
		path: string;
	}
	var pages: Page[] = [
		{ path: '/about', title: 'About' },
		{ path: '/survey', title: 'Survey' },
		{ path: '/graph', title: 'Graph' }
	];
</script>

<header class="flex items-center justify-between px-10">
	<a href="/" class="font-extrabold p-5 transition-all hover:scale-125">AI in coding</a>
	<div>
		{#each pages as page}
			<a href={page.path} class="p-5 opacity-50 transition-all hover:opacity-100 ">{page.title}</a>
		{/each}
	</div>
</header>

<style>
</style>
