<script lang="ts">
	import Footer from '$lib/components/footer/Footer.svelte';
	import Header from '$lib/components/header/Header.svelte';
	import '../app.css';
</script>

<Header />

<main style="min-height: calc(100vh - 8.5rem)">
	<slot />
</main>

<Footer />
