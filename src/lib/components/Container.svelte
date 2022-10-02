<script lang="ts">
	export let noGlutter = false;
</script>

<main class="{!noGlutter ? 'md:w-3/5 w-100' : 'w-100'} mx-auto">
	<slot />
</main>
