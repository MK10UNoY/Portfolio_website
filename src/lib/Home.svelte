<script>
	export let title = 'Welcome to My Website';
	export let subtitle = 'We create amazing web experiences';
	export let buttonText = 'Get Started';
	export let buttonLink = '#';
</script>

<section class="hero">
	<h1>{title}</h1>
	<p>{subtitle}</p>
	<a href={buttonLink}>{buttonText}</a>
</section>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap');

	.hero {
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		height: 100vh;
		color: #0ff;
		padding: 0 2rem;
		overflow: hidden;
		font-family: 'Orbitron', sans-serif;
	}

	.hero::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
		z-index: -2;
	}

	.hero svg {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
	}

	.hero h1 {
		font-size: 3rem;
		margin-bottom: 1rem;
		text-shadow:
			0 0 10px #0ff,
			0 0 20px #0ff,
			0 0 30px #0ff;
	}

	.hero p {
		font-size: 1.5rem;
		margin-bottom: 2rem;
		text-shadow:
			0 0 10px #0ff,
			0 0 20px #0ff,
			0 0 30px #0ff;
	}

	.hero a {
		display: inline-block;
		padding: 1rem 2rem;
		font-size: 1rem;
		color: #0ff;
		background-color: #222;
		border: 2px solid #0ff;
		border-radius: 5px;
		text-decoration: none;
		transition:
			background-color 0.3s ease,
			color 0.3s ease;
		text-shadow:
			0 0 10px #0ff,
			0 0 20px #0ff,
			0 0 30px #0ff;
	}

	.hero a:hover {
		background-color: #0ff;
		color: #222;
	}
</style>
