<script>
	let titles = ["a developer", "a systems architect", "a creative thinker", "an innovator"];
	let currentTitle = "";
	let index = 0;
	let subIndex = 0;
	let isDeleting = false;
	let typingSpeed = 75;

	function typeWriter() {
		currentTitle = isDeleting
				? titles[index].substring(0, subIndex--)
				: titles[index].substring(0, subIndex++);

		if (!isDeleting && subIndex === titles[index].length) {
			// Switch to deleting mode after a pause
			setTimeout(() => (isDeleting = true), 1000);
		} else if (isDeleting && subIndex === 0) {
			// Switch to next title after deleting
			isDeleting = false;
			index = index < titles.length - 1 ? index + 1 : 0;
		}

		setTimeout(typeWriter, typingSpeed);
	}

	// Start the typewriter effect when the component mounts
	typeWriter();
</script>

<style>
	@media screen and (max-width: 600px) {
		.title {
			margin: 0; /* Full centering on mobile */
		}
	}

	.container {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		height: 100vh; /* Take full viewport height */
		width: 100vw;
	}

	.title {
		font-family: ErbosDracoRegularOpen, monospace;
		font-size: xxx-large;
		margin-left: 10vw;
		margin-top: 40vh;
	}

	.cursor {
		display: inline-block;
		width: 0.8ch; /* ch units to match the width of a character */
		height: 1em; /* em units to match the height of a line */
		background-color: limegreen;
		margin-left: 2px; /* Optional: adds a small space between text and cursor */
		vertical-align: bottom; /* Aligns with the baseline of the text */
		animation: blink 1s step-end infinite;
	}

	@keyframes blink {
		50% {
			opacity: 0;
		}
	}

	.coming-soon {
		text-align: center;
		font-size: larger;
	}

	.coming-soon img {
		width: 42px;
		height: 42px;
		vertical-align: middle;
		padding-right: 10px;
	}

	.footer {
		margin-bottom: 10px;
		text-align: center;
		font-size: 0.8em;
	}

	.attribution {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.svelte-logo {
		height: 1em;
		margin-right: 5px;
	}
</style>

<div class="container">
	<main>
		<div class="title">
			Wesley is <span>{currentTitle}</span><span class="cursor"></span>
		</div>
	</main>

	<div class="coming-soon">
		<p>More coming soon!</p>
		<a href="https://github.com/wesaka" target="_blank"><img src="/github-mark-white.svg" alt="GitHub Link"/></a>
		<a href="https://linkedin.com/in/wesaka" target="_blank"><img src="/linkedin-rounded-svgrepo-com.svg" alt="Linkedin Link"/></a>
		<a href="mailto:connect@wesley.com.es"><img src="/envelope-fill-svgrepo-com.svg" alt="Send me an email!"/></a>
	</div>

	<div class="footer">
		<div class="attribution">
			<img src="/svelte-svgrepo-com.svg" alt="Svelte Logo" class="svelte-logo" />
			<span>Built with Svelte |</span>
			<a href="/attribution-link"> Attributions</a>
		</div>
	</div>
</div>