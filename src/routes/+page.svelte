<!-- //<script>
//	import Home from '$lib/Home.svelte';
//	import About from '$lib/About.svelte';
//	import Projects from '$lib/Projects.svelte';
//	import Contact from '$lib/Contact.svelte';
//	import Footer from '$lib/Footer.svelte';
//</script>

//<Home />
//<About />
//<Projects />
//<Contact />
//<Footer /> -->

<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';

	onMount(() => {
		goto('https://mk10unoy.github.io/mrinmoykoiri_portfolio/'); // Replace with your actual route
	});
</script>
