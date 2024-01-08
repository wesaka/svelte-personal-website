<script>
	import github from '$lib/images/github-mark-white.svg';
	import linkedin from '$lib/images/linkedin-rounded-svgrepo-com.svg';
	import email from '$lib/images/envelope-fill-svgrepo-com.svg'

	let titles = [
		"a fullstack developer",
		"a database architect",
		"a problem solver",
		"a cloud enthusiast",
		"a data scientist",
		"a cybersecurity expert",
		"a machine learning aficionado",
		"an open source contributor",
		"a UX/UI designer",
		"a systems architect",
		"a DevOps specialist",
		"an IoT innovator",
		"a network architect",
		"a blockchain developer",
		"a software engineer",
		"an AI researcher",
		"a digital nomad",
		"a startup enthusiast"
	];
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

<svelte:head>
	<title>Wesley</title>
	<meta name="description" content="Wesley's personal website" />
</svelte:head>

<section class="container">
	<div class="title">
		>Wesley is <span>{currentTitle}</span><span class="cursor"></span>
	</div>

	<div class="coming-soon">
		<p>More coming soon!</p>
		<a href="https://github.com/wesaka/svelte-personal-website" target="_blank">
			<img src={github} alt="Github Link" />
		</a>
		<a href="https://linkedin.com/in/wesaka" target="_blank">
			<img src={linkedin} alt="Linkedin Link"/>
		</a>
		<a href="mailto:connect@wesley.com.es">
			<img src={email} alt="Send me an email!"/>
		</a>
	</div>
</section>

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
		font-size: xx-large;
		margin-left: 10vw;
		margin-top: 40vh;
		word-wrap: break-word;
		word-break: break-word;
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
		margin-bottom: 15vh;
	}

	.coming-soon img {
		width: 42px;
		height: 42px;
		vertical-align: middle;
		padding-right: 10px;
	}

</style>