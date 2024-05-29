<svelte:head>
	<title>3D genomics @ HIDIVE</title>
	<meta name="description" content="Visualization of three-dimensional (3D) genomic data at the HIDIVE lab" />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap" rel="stylesheet">
</svelte:head>

<div id="body-wrapper">
	<h1>3D genomic data visualization @ HIDIVE lab</h1>
	<p>
	We are a group of data visualization-focused researchers at the <a href="http://hidivelab.org">HIDIVE lab</a>. Our goal is to empower scientists working with complex data by making easy-to-use visualization tools. We primarily focus on data from biology and medicine.
	</p>
	<p>This webpage summarizes our efforts in improving the tooling for visualization of three-dimensional (3D) genomic data.</p>

	<!-- <p> -->
	<!-- 	People: David Kouril, Nils Gehlenborg. -->
	<!-- </p> -->

	<h2>Motivation</h2>
	<!-- first paragraph generally about chromatin folding -->
	<p>Methods for determining the structural conformation of chromatin (i.e., DNA + supporting proteins) lean heavily on Hi-C and ChIP-Seq (and their variations) for probing the spatial organization of genomes. These methods however produce data in a two-dimensional (2D) visual representation&mdash;a heatmap&mdash;encoding likeliness of interactions between genomic regions.
	Orthogonally to that, biologists used computer simulation to model the chromatin folding in silico. Such modeling methods ultimately produce an actual three-dimensional prediction of the genome structure.</p>

	<!-- second paragraph about how visualization tool for this suck -->
	<p>Due to the similarity of chromatin models to protein structure, many of the existing proteomics visualization tools and data formats have been adopted by the chromatin modelling community. There are, however, key differences between models of proteins and chromatin, and the genomics use case requires tools with proper semantics. Furthermore, the tools that have developed for 3D genomics so far are often developed as one-off publications without intention of integration into computational biologists' workflow, thus limiting their adoption and extensibility.</p>
	<!-- <p>Many tools have been developed for genomics and investigation of chromatin's spatial structure is important. However, the tools currently used in day-to-day practice are mostly from proteomics.</p> -->

	<p>This topic has utility in two aspects: giving proper tools to computational biologists; and addressing data visualization challenges. From the data visualization research perspective, we are interested in:</p>
	<ul>
		<li>The <b>interplay between 2D visualizations</b>, such as standard statistical plots or genome browsers, and <b>3D representations</b>: 3D visualization has occupied a special place in data visualization, reserved for describing spatial phenomena. The need to project 3D structures onto a 2D screen leads to occlusion, which is one of the issues often mentioned related to 3D visualization. Our research question is about the utility of 3D visualization and how best to link with other visual representations.</li>
		<li>Making <b>visualizations for computational notebooks</b>: Many data visualization tools from our community exist as standalone tools that elicit importing/exporting and therefore rely on strong file format standardization in subdomains. This approach often results in data visualization research being developed in silos, separated from the actual potential users. Computational notebooks have emerged as an environment where day-to-day data analysis work happens. We are therefore interested in exploring how to make data visualization tools available where users can use them with very little barrier of entry.</li>
	</ul>

	<p>
	</p>

	<h2>Software</h2>
	<div class="legend-wrapper">
		<span class="legend">
		🚧 = still heavily work in progress. ⌨️ = still developed, but should be usable. ✅ = (mostly) finished!<br/>
		</span>
	</div>
	<p>🚧 <b>chromospace</b>: javascript library for visualization of 3D chromatin structures<br/>
	<span class="sw-links"><a href="https://github.com/dvdkouril/chromospace">github</a> | <a href="https://observablehq.com/@david-kouril/chromospace-playground">observablehq example</a> | <a href="https://jsr.io/@chromospace/chromospace">jsr</a></span>
	</p>
	<p>🚧 <b>chromospyce</b>: anywidget-powered computational notebook version of chromospace
	<span class="sw-links"><a href="https://github.com/dvdkouril/chromospyce">github</a> | <a href="https://colab.research.google.com/drive/1E-jDzM1hs-TtTg_XJnEuDn6RU2VG0Lxe?usp=sharing">google colab example</a></span>
	</p>

	<h2>Writing</h2>
	<p>🚧 <a href="https://www.davidkouril.com/really-3d-genome/">Visualizing 3D genomic data</a>: overview of 3D genome modeling and visualization, intended as an introduction into the topic for data visualization researchers.</p>
	<p>🚧 <a href="https://www.davidkouril.com/hyperwindows-paper/">Exploring Genomes in 3D Using a Non-uniform Physics-Based Layout</a>: paper primarily written about the hyperwindows method.</p>

	<h2>Roadmap</h2>
	<p>Yes, we will have a roadmap.</p>
	<ul>
		<li>Declarative grammar specification for 3D genomic data.</li>
		<li>Integration in <a href="http://gosling-lang.org">Gosling</a>.</li>
	</ul>

	<h2>Other prototypes</h2>
	<ul>
	<li>
		<p><b>hierarchical-selections prototype</b>: hierarchical selections in a 3D chromatin model, visualization via a fixed tree-like layout.
		<span class="sw-links"><a href="https://github.com/dvdkouril/hierarchical-selections">github</a> | <a href="https://dvdkouril.github.io/hierarchical-selections/">app</a></span>
		</p>
	</li>
	<li>
		<p><b>hyperwindows</b>: a prototype for a novel visualization technique for navigating complex 3D structures via a hierarchical layouting and interactions.
		<span class="sw-links"><a href="https://github.com/dvdkouril/chromatin-n-out">github</a> | <a href="https://www.davidkouril.com/chromatin-n-out/">app</a></span>
		</p>
	</li>
	</ul>

	<h2>Student topics</h2>
	<p><i>We are generally very excited to work with undergraduate students through interships, term projects, etc. The prerequisites are coding skills and interest in research. For our current focus, it is also recommended to have some background and an interest in real-time computer graphics. Below, we list few work packages that you could work on.</i></p>

	<p><b>High quality figure outputs with Blender:</b> The idea is to build a 3D chromatin visualization interactively using chromospace, using the declarative specification, and then use Blender to produce a high-quality and high-resolution rendering. Maybe it could be useful to leverage the ecosystem around glTF, for example <a href="https://gltf-transform.dev">glTF Transform</a>.</p>
</div>

<style>
* {
	font-family: "Dosis", sans-serif;
}
:global(body) {
	background-color: #111827;
	}

@media screen and (min-width: 1000px) {
	#body-wrapper {
		width: 800px;
		margin: 0 auto;
	}
}
#body-wrapper {
	color: white;
	text-align: justify;
	line-height: 1.3;
	font-size: 120%;
}
a {
	color: #f0abfc;
}
h1, h2, h3 {
	color: #DDD6FE;
}
.sw-links {
	display: block;
	text-align: center;
}
.legend {
	font-size: 80%;
	display: inline-block;
	border: 1px dashed white;
	padding: 10px;
}
.legend-wrapper {
	text-align: center;
}
ul li {
	margin-bottom: 20px;
}
</style>
