<script lang="ts">
	import blueskyLogo from "$lib/logos/bluesky.svg";
	import githubLogo from "$lib/logos/github.svg";
	import observableLogo from "$lib/logos/observable.svg";
</script>

<svelte:head>
	<title>Hello world!</title>
	<meta
		name="description"
		content="This is where the description goes for SEO"
	/>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div id="container">
	<div id="job-search">
		<p>
			I'm searching for my next research role: <br />
			<a href="/cv">CV</a> <br />
		</p>
	</div>

	<p>
		Hi, I'm currently a postdoc at <a href="http://hms.harvard.edu"
			>Harvard Medical School</a
		>
		in Nils Gehlenborg's <a href="http://hidivelab.org">HIDIVE Lab</a>.
	</p>

	<p>
		My research work centers around data visualization, with a special focus
		on data with spatial components. I work at the intersection of
		disciplines, bridging software development, computer graphics, and
		biology. I'm especially interested in developing new interaction
		techniques that make complex or unfamiliar type of data more intuitive
		to grasp and explore.
	</p>

	<p>
		At HIDIVE, I investigate visualization of 3D chromatin structure
		predictions as a complement for the typical chromosome conformation
		capture techniques used for determining spatial organization of genomes.
		This involves developing <a
			href="https://observablehq.com/@david-kouril/chromospace-playground"
			>new web-based visualization software</a
		>, as well as an interface for
		<a href="https://github.com/dvdkouril/chromospyce"
			>computational notebooks</a
		>.
	</p>

	<p>
		I received a doctoral degree from <a href="https://www.tuwien.at/en/"
			>TU Wien</a
		>. My thesis
		<em
			>Interactive Visualization of Dense and Multi-Scale Data for Science
			Outreach</em
		>
		was awarded the
		<a
			href="https://www.eg.org/wp/eurographics-awards-programme/eurovis-phd-award/"
			>EuroVis PhD Award in 2022</a
		>.
	</p>

	<p>
		I was born in <a href="https://maps.app.goo.gl/ctHG1FnMsnKei2FN7"
			>Zlín, Czech Republic</a
		>, and lived in
		<a href="https://maps.app.goo.gl/e4W2jxMeZuTjPTFW9">Brno</a> for several
		years.
	</p>
	<div id="links">
		<a class="socials-logo" href="https://bsky.app/profile/dvdkouril.xyz"
			><img alt="bluesky logo" src={blueskyLogo} /></a
		>
		|
		<a class="socials-logo" href="https://github.com/dvdkouril"
			><img alt="github logo" src={githubLogo} /></a
		>
		|
		<a class="socials-logo" href="https://observablehq.com/@david-kouril"
			><img alt="observablehq logo" src={observableLogo} /></a
		>
	</div>
</div>

<style>
	* {
		font-family: "Dosis", sans-serif;
	}

	#container {
		width: 100%;
		max-width: 440px;
		text-align: justify;
		line-height: 1.3;
		font-size: 110%;
	}

	h1 {
		padding-bottom: 0;
		margin-bottom: 0;
		font-size: 2.2em;
	}

	h2 {
		color: #aaaaaa;
		padding-top: 0;
		margin-top: 0;
		font-size: 1.65em;
	}
	h2 > pre {
		padding-top: 0;
		margin-top: 0;
	}

	a {
		color: black;
		font-size: 90%;
		/*background-color: red;*/
		padding: 0px 5px 0px 5px;
		margin-top: 5px;
		text-decoration: underline;
		text-decoration-thickness: 5px;
	}

	a:hover {
		background-color: red;
		text-decoration: underline;
		text-decoration-thickness: 5px;
		text-decoration-color: blue;
		color: white;
	}

	#links {
		text-align: center;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 5px;
	}
	.socials-logo img {
		height: 25px;
	}
	.socials-logo {
		background-color: transparent;
	}
	.socials-logo:hover {
		background-color: transparent;
		text-decoration: none;
		color: white;
		font-size: 90%;
		padding: 0px 5px 0px 5px;
		margin-top: 5px;
		text-decoration: none;
	}
	#job-search {
		text-align: center;
	}
	#job-search p {
		display: inline-block;
		text-align: center;
		border: 2px solid black;
		padding: 10px 8px 10px 8px;
	}
</style>
