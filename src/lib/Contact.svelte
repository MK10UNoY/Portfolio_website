<script lang="ts">
	import { onMount } from 'svelte';
	import emailjs from 'emailjs-com';

	let name = '';
	let email = '';
	let message = '';

	function sendEmail() {
		emailjs
			.send(
				'YOUR_SERVICE_ID',
				'YOUR_TEMPLATE_ID',
				{
					from_name: name,
					from_email: email,
					message: message
				},
				'YOUR_USER_ID'
			)
			.then(
				(response: { status: number; text: string }) => {
					console.log('SUCCESS!', response.status, response.text);
				},
				(err: any) => {
					console.log('FAILED...', err);
				}
			);
	}
</script>

<div class="mx-auto max-w-lg rounded-lg bg-gray-800 p-6 text-white shadow-md">
	<h2 class="mb-4 text-2xl font-bold">Contact Me</h2>
	<form on:submit|preventDefault={sendEmail} class="space-y-4">
		<input
			type="text"
			placeholder="Your Name"
			bind:value={name}
			required
			class="w-full rounded-md bg-gray-700 p-3 focus:ring-2 focus:ring-blue-500 focus:outline-none"
		/>
		<input
			type="email"
			placeholder="Your Email"
			bind:value={email}
			required
			class="w-full rounded-md bg-gray-700 p-3 focus:ring-2 focus:ring-blue-500 focus:outline-none"
		/>
		<textarea
			placeholder="Your Message"
			bind:value={message}
			required
			class="w-full rounded-md bg-gray-700 p-3 focus:ring-2 focus:ring-blue-500 focus:outline-none"
		></textarea>
		<button
			type="submit"
			class="w-full rounded-md bg-blue-600 p-3 hover:bg-blue-700 focus:ring-2 focus:ring-blue-500 focus:outline-none"
			>Send</button
		>
	</form>
</div>

<div class="background">
	<svg viewBox="0 0 800 400">
		<circle cx="400" cy="200" r="200" fill="blue" />
	</svg>
	<img
		src="https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif"
		style="top: 10%; left: 10%;"
	/>
	<img
		src="https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif"
		style="top: 50%; left: 50%;"
	/>
	<img
		src="https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif"
		style="top: 80%; left: 80%;"
	/>
</div>

<style>
	.background {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
		overflow: hidden;
	}

	.background svg {
		position: absolute;
		width: 100%;
		height: 100%;
		opacity: 0.1;
	}

	.background img {
		position: absolute;
		width: 100px;
		height: 100px;
		animation: float 5s infinite ease-in-out;
	}

	@keyframes float {
		0% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-20px);
		}
		100% {
			transform: translateY(0);
		}
	}
</style>
