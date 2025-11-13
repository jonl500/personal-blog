<script lang="ts">
	import '../app.css';
	import Footer from '$lib/components/footer.svelte'
	import Header from '$lib/components/header.svelte'
	import favicon from '$lib/assets/favicon.svg';

	let { children, data } = $props();
</script>
<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>
<div class="layout">
	<Header />
	<main>
		{@render children?.()}
	</main>
	<Footer />
</div>

<style>
	.layout {
		height: 100%;
		max-inline-size:  1440px; /*this is the max width of the page*/
		display: grid; /*this is the layout of the page*/
		grid-template-rows: auto 1fr auto; /*this is the height of the header, main, and footer*/
		margin-inline: auto; /*this is the margin of the page*/
		padding-inline: var(--size-7); /*this is the padding of the page*/
	
		@media (min-width: 1440px) {
			padding-inline: 0;
		}
	}

	main {
		padding-block: var(--size-7);
	}
</style>