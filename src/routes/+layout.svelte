<script lang="ts">
	import Footer from './footer.svelte'
	import Header from './header.svelte'
	import PageTransition from './transition.svelte'

	import '../app.css'

	export let data
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@700&family=Montserrat:wght@500&family=Rubik:wght@300&display=swap" rel="stylesheet"> 
</svelte:head>

<div class="layout">
	<Header />

	<main>
		
		<PageTransition url={data.url}>
			<slot />
		</PageTransition>
	</main>

	<Footer />
</div>

<style>
	/* @import url('$lib/reset.css');
	@import url('$lib/theme.css'); */

	/* .wrapper {
		color: var(--t-text);
		max-width: 50rem;
		margin: auto;
	} */
	.layout {
		height: 100%;
		max-inline-size: var(--page-width);
		display: grid;
		grid-template-rows: auto 1fr auto;
		margin-inline: auto;
		padding: 1rem;
	}

	main {
		padding-block: 1rem;
  margin-bottom: 1rem;
  margin-top: -2rem;
	}

	@media (min-width: --page-width) {
		.layout {
			/* padding: 0; */
		}
	}
</style>
