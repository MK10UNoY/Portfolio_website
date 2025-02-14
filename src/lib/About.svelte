<div class="about" id="about">
	<div class="contentBx" data-sal="slide-right" data-sal-delay="300">
		<h2 class="heading">About</h2>
		<p class="txt">
			Greetings, myself Mrinmoy Koiri. Here's a bit about what I do...
			<br /><br />
			With a blend of creativity and technical expertise, I transform ideas into functional and visually
			appealing websites. Whether it’s front-end magic with HTML, CSS, and JavaScript, or diving into
			back-end technologies, I thrive on solving challenges and bringing digital visions from design
			files lying in Figma to just a simple idea in one's mind.
		</p>
	</div>
	<div class="imgBx" data-sal="slide-left" data-sal-delay="300" id="selfimg"></div>
</div>

<style>
	.about {
		position: relative;
		width: 100%;
		background: #162c3b;
		display: flex;
	}
	.about .contentBx {
		background: #162c3b;
		padding: 100px;
		width: 40vw;
	}
	.about .imgBx {
		position: relative;
		width: calc(0.7 * 100vh);
		height: calc(0.9 * 100vh);
		margin: 4%;
		border-radius: 10px;
		background: url('../assets/self.jpg');
		background-size: cover;
		background-position: center;
		transition: all 0.6s;
		overflow-y: hidden;
	}
	.about .imgBx::after {
		content: '';
		position: absolute;
		width: calc(0.7 * 100vh);
		height: calc(0.9 * 100vh);
		border-radius: 10px;
		background: transparent;
		backdrop-filter: blur(14px);
		z-index: 19;
		transition: all 0.6s;
	}
	.about .imgBx:hover::after {
		content: '';
		position: absolute;
		width: calc(0.7 * 100vh);
		height: calc(0.9 * 100vh);
		border-radius: 10px;
		background: transparent;
		backdrop-filter: blur(0px);
		z-index: 19;
	}
	.about .imgBx:hover {
		position: relative;
		width: calc(0.6 * 100vh);
		height: calc(0.8 * 100vh);
		margin: 7%;
		box-shadow: 0px 0px 15px 5px rgb(0, 149, 255);
		border-radius: 50px;
		background: url('../assets/self.jpg');
		background-size: cover;
		background-position: center;
	}
	.txt {
		color: #fff;
		font-size: 1.4em;
		font-weight: 300;
		letter-spacing: 1px;
		line-height: 30px;
	}
</style>
