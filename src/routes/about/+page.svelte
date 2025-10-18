<script lang="ts">
</script>

<svelte:head>
	<title>about.</title>
	<!--<meta
		name="description"
		content="This is where the description goes for SEO"
	/>-->
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div id="container">
	<h2>about.</h2>
	<p>
		I was born in <a href="https://maps.app.goo.gl/ctHG1FnMsnKei2FN7"
			>Zlín, Czech Republic</a
		>, and lived in
		<a href="https://maps.app.goo.gl/e4W2jxMeZuTjPTFW9">Brno</a> for several
		years.
	</p>
	<p>I do jiujitsu.</p>
	<p>
		Other things that I was at some point extremely into: digital painting,
		indie rock, playing the guitar.
	</p>
</div>

<style>
	* {
		font-family: "Dosis", sans-serif;
	}

	#container {
		width: 100%;
		max-width: 800px;
		font-size: 110%;
	}
</style>
