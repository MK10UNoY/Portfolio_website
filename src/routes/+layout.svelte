<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { onMount } from 'svelte';

	let cursorX = $state(0);
	let cursorY = $state(0);
	let trails = $state<{ x: number; y: number; id: string }[]>([]);

	function createTrail(x: number, y: number) {
		const id = Math.random().toString(36).substr(2, 9);
		trails = [...trails, { x, y, id }];
		const trailDuration = 500; // Set the trail duration here (in milliseconds)
		setTimeout(() => {
			trails = trails.filter((trail) => trail.id !== id);
		}, trailDuration);
	}

	onMount(() => {
		window.addEventListener('mousemove', (e) => {
			cursorX = e.clientX;
			cursorY = e.clientY;
			createTrail(e.clientX, e.clientY);
		});
	});
</script>

<div class="cursor" style="top:{cursorY}px; left:{cursorX}px;"></div>
{#each trails as trail (trail.id)}
	<div class="trail" style="top:{trail.y}px; left:{trail.x}px;"></div>
{/each}

{@render children()}

<style>
	.cursor {
		position: fixed;
		width: 40px;
		height: 40px;
		border-radius: 50%;
		background-color: rgba(0, 0, 0, 0.7);
		pointer-events: none;
		transform: translate(-50%, -50%);
	}
	.trail {
		position: fixed;
		width: 15px;
		height: 15px;
		border-radius: 50%;
		background-color: rgb(255, 255, 255);
		pointer-events: none;
		transform: translate(-50%, -50%);
		transition: opacity 0.001s ease-out;
	}
</style>
