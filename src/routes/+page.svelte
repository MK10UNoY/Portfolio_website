//<script>
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
//<Footer />

<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';

	onMount(() => {
		goto('/newpage'); // Replace with your actual route
	});
</script>
