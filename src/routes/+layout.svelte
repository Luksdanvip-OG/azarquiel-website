<script>
	import Navbar from '../components/Navbar.svelte';
	import InfoHeader from '../components/InfoHeader.svelte';
	import InfoFooter from '../components/InfoFooter.svelte';
	import {fly} from 'svelte/transition';
	import PageTransition from '../components/animations/PageTransition.svelte';
	import { onMount } from 'svelte';
  	let ready = false;
  	onMount(() => ready = true);
</script>

{#if ready}
<div class="container-fluid" transition:fly="{{ y: 200, duration: 2000 }}">
	<InfoHeader/>
	<header class="sticky-top">
		<Navbar />
	</header>
	
		<main>
			<slot />
		</main>

	<footer>
		<InfoFooter/>
	</footer>
</div>
{/if}
<style lang="sass">
	@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap')
	*
		margin: 0
		padding: 0
		font-family: 'Open Sans', sans-serif
		font-weight: 300
</style>
