<svelte:head>
	<title>Hello world!</title>
	<meta name="description" content="This is where the description goes for SEO" />
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap" rel="stylesheet">
</svelte:head>

<h1>DAVID KOUŘIL.</h1>
<h2><pre>David Kou\v{'{'}r{'}'}il</pre></h2>

<div id="container">
	<p>Hi, I'm currently a postdoc at <a href="http://hms.harvard.edu">Harvard Medical School</a> in Nils Gehlenborg's <a href="http://hidivelab.org">HIDIVE Lab</a>.</p>

	<p>I work in data visualization research, specializing on biological data. At HIDIVE, I develop tools for visualization of 3D chromatin structure predictions as a complement for the typical chromosome conformation capture techniques used for determining spatial organization of genomes.</p>

	<p>Currently, I'm making a Javascript <a href="https://observablehq.com/@david-kouril/chromospace-playground">library for 3D chromatin visualization</a>. We're also preparing a widget version intended for use in <a href="https://github.com/dvdkouril/chromospyce">computational notebooks</a>.</p>

	<p>I received a doctoral degree from <a href="https://www.tuwien.at/en/">TU Wien</a>. My thesis <em>Interactive Visualization of Dense and Multi-Scale Data for Science Outreach</em> was awarded the <a href="https://www.eg.org/wp/eurographics-awards-programme/eurovis-phd-award/">EuroVis PhD Award in 2022</a>.</p>

	<p>I was born in <a href="https://maps.app.goo.gl/ctHG1FnMsnKei2FN7">Zlín, Czech Republic</a>, and lived in <a href="https://maps.app.goo.gl/e4W2jxMeZuTjPTFW9">Brno</a> for several years.</p>
</div>


<style>
* {
	font-family: "Dosis", sans-serif;
}

#container {
	width: 440px;
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
	color: white;
	font-size: 90%;
	background-color: red;
	padding: 0px 5px 0px 5px;
	margin-top: 5px;
	text-decoration: none;
	}
</style>
