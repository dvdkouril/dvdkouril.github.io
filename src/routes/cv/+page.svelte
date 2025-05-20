<script lang="ts">
	import * as Plot from "@observablehq/plot";
	import * as d3 from "d3";

	let div: HTMLDivElement;
	let data = d3.ticks(-2, 2, 200).map(Math.sin);

	type ReviewEntry = {
		date: string;
		venue: string;
		count?: number;
		note?: string;
	};

	/*
	some decisions:
	- What to capture when reviewing for a conference that happens the year after I actually do the review?
	*/
	let reviewsData: ReviewEntry[] = [
		// IEEE Vis 2018 (InfoVis)
		{
			date: "2018",
			venue: "IEEE VIS",
			note: "InfoVis",
		},
		// EuroVis 2019
		{
			date: "2019",
			venue: "EuroVis",
		},
		// CESCG 2019
		{
			date: "2019",
			venue: "CESCG",
		},
		// IEEE TVCG (Jan2020, Apr2021)
		{
			date: "2020",
			venue: "IEEE TVCG",
			note: "Jan",
		},
		{
			date: "2021",
			venue: "IEEE TVCG",
			note: "Apr",
		},
		// IEEE Vis 2020 (InfoVis, SciVis)
		{
			date: "2020",
			venue: "IEEE VIS",
			note: "InfoVis",
		},
		{
			date: "2020",
			venue: "IEEE VIS",
			note: "SciVis",
		},
		// IEEE Vis 2021
		{
			date: "2021",
			venue: "IEEE VIS",
		},
		// ISMAR 2021
		{
			date: "2021",
			venue: "ISMAR",
		},
		// EuroVis 2022
		{
			date: "2022",
			venue: "EuroVis",
		},
		{
			date: "2022",
			venue: "EuroVis",
		},
		// IEEE Vis 2022
		{
			date: "2022",
			venue: "IEEE VIS",
		},

		//~ from ubercv
		// IEEE VIS 2024
		{
			date: "2024",
			venue: "IEEE VIS",
		},
		// Frontiers in Bioinformatics
		{
			date: "2024",
			venue: "Frontiers in Bioinformatics",
		},
		// Computers & Graphics Oct 2024
		{
			date: "2024",
			venue: "Computers & Graphics",
		},
		// PacificVis 2025
		{
			date: "2024",
			venue: "PacificVis",
			count: 3,
			note: "IPC",
		},
		{
			date: "2024",
			venue: "PacificVis",
			count: 3,
		},
		{
			date: "2024",
			venue: "PacificVis",
			count: 3,
		},
		// CHI 2025
		{
			date: "2024",
			venue: "ACM CHI",
		},

		//~ from PCS
		// EuroVis 2024
		{
			date: "2024",
			venue: "EuroVis",
		},
		// EuroVis 2023 x2
		{
			date: "2023",
			venue: "EuroVis",
		},
		{
			date: "2023",
			venue: "EuroVis",
		},
		// VIS 2023 x3
		{
			date: "2023",
			venue: "IEEE VIS",
		},
		{
			date: "2023",
			venue: "IEEE VIS",
		},
		{
			date: "2023",
			venue: "IEEE VIS",
		},

		// {
		// 	date: "2024",
		// 	venue: "IEEE VIS",
		// },
		// {
		// 	date: "2024",
		// 	venue: "Frontiers in Bioinformatics",
		// },
		// {
		// 	date: "2024",
		// 	venue: "Computers and Graphics",
		// },
		// {
		// 	date: "2024",
		// 	venue: "PacificVis",
		// 	count: 3,
		// },
		// {
		// 	date: "2024",
		// 	venue: "PacificVis",
		// 	count: 3,
		// },
		// {
		// 	date: "2024",
		// 	venue: "PacificVis",
		// 	count: 3,
		// },
		// {
		// 	date: "2024",
		// 	venue: "CHI",
		// },
		// {
		// 	date: "2023",
		// 	venue: "CHI",
		// },
		// {
		// 	date: "2023",
		// 	venue: "CHI",
		// },
		// {
		// 	date: "2022",
		// 	venue: "CHI",
		// },
	];

	function onMousemove(event: MouseEvent) {
		const [x, y] = d3.pointer(event);
		data = data.slice(-200).concat(Math.atan2(x, y));
	}

	$: {
		div?.firstChild?.remove(); // remove old chart, if any
		div?.append(
			Plot.plot({
				width: 928,
				height: 250,
				x: { label: null },
				y: { tickFormat: "s", tickSpacing: 50 },
				color: {
					legend: true,
					scheme: "Spectral",
				},
				marks: [
					Plot.barY(
						reviewsData,
						Plot.groupX(
							{ y: "count" },
							{ x: "date", fill: "venue", stroke: "red" },
						),
					),
				],
			}),
		);
	}
</script>

<svelte:head>
	<title>cv.</title>
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
	<h2>basic information.</h2>
	<div style="margin-left: 40px">
		<p>Full name: Dr.techn. Mgr. David Kouril.</p>
		<p>Nationality: Czech.</p>

		<p>Links: bsky, github, observable.</p>
	</div>

	<h2>education.</h2>
	<ul>
		<li class="cv-item">
			<div class="date-column">Mar 2017 - Apr 2021:</div>
			<div class="item-details">
				<strong>Doctoral Degree (Dr.techn.)</strong> @ TU Wien (AT)
				<br />
				Thesis:
				<i
					>“Interactive Visualization of Dense and Multi-Scale Data
					for Science Outreach”</i
				>
			</div>
		</li>
		<li class="cv-item">
			<div class="date-column">Sep 2014 - Feb 2017:</div>
			<div class="item-details">
				<strong>Master's Degree (Mgr.)</strong> @ Masaryk University
				(CZ)
				<br />
				Field: Computer Graphics, Thesis:
				<i
					>"Maya2CellVIEW: Integrated Tool for Creating Large and
					Complex Molecular Scenes"</i
				>
			</div>
		</li>
		<li class="cv-item">
			<div class="date-column">Sep 2011 - Jun 2014:</div>
			<div class="item-details">
				<strong>Bachelor's Degree (Bc.)</strong> @ Masaryk University
				(CZ)
				<br />
				Field: Computer Graphics and Image Processing, Thesis:
				<i>"Fast region labeling of binary images"</i>
			</div>
		</li>
	</ul>

	<h2>awards.</h2>
	<ul class="basic-list">
		<li>
			<a
				href="https://ieeevis.org/year/2018/info/awards/best-paper-awards#scivis"
				>IEEE Vis 2018 Best Paper Honorable Mention (SciVis)</a
			>
		</li>
		<li>
			<a
				href="https://www.eg.org/wp/eurographics-awards-programme/eurovis-phd-award/"
				>EuroVis Best PhD Award 2022</a
			>
		</li>
	</ul>

	<h2>research experience.</h2>
	<ul>
		<li class="cv-item">
			<div class="date-column">Jul 2023 - Jun 2025:</div>
			<div class="item-details">
				<strong>Postdoctoral Research Fellow</strong> @ Harvard Medical School
				(USA)
			</div>
		</li>
		<li class="cv-item">
			<div class="date-column">Jul 2021 - Jun 2023:</div>
			<div class="item-details">
				<strong>Postdoctoral Researcher</strong> @ Masaryk University
				(CZ)

				<ul>
					<li>
						Leading role in a project dealing with visualization of
						three-dimensional chromatin models
					</li>
					<li>
						Advising doctoral students at the visualization group
						VisitLab
					</li>
					<li>
						Contributed to writing project proposal submitted to
						GAČR (Czech Science Foundation), funded in December 2022
					</li>
				</ul>
			</div>
		</li>
		<li class="cv-item">
			<div class="date-column">Mar 2017 - Feb 2021:</div>
			<div class="item-details">
				<strong>Project Assistant</strong> @ TU Wien (AT)

				<ul>
					<li>
						Main researcher for 3 research projects Labels on
						Levels: labeling for molecular scenes HyperLabels:
						multi-scale navigation Molecumentary: virtual tours of
						molecular models
					</li>
					<li>
						Provided support to students and external collaborators
						with the Marion library
					</li>
					<li>
						Collaborated with international experts from both
						visualization and biology domain
					</li>
				</ul>
			</div>
		</li>
		<li class="cv-item">
			<div class="date-column">Jul 2016 - Feb 2017:</div>
			<div class="item-details">
				<strong>Project Assistant Without Degree</strong> @ TU Wien
				<ul>
					<li>
						Integrated several research prototypes into a unified
						demo which was then submitted to the VIZZIES challenge
						(organized by National Science Foundation)
					</li>
					<li>
						Ported a high-performance molecular rendering technique
						(cellVIEW) from DirectX to OpenGL for a new proprietary
						library (called Marion)
					</li>
					<li>
						This code was later used in commercialization of the
						Marion library by a spin-off company Nanographics GmbH
					</li>
					<li>
						Implemented nano-scale rendering of microtubules for a
						project contracted by Allen Institute For Cell Science
					</li>
				</ul>
			</div>
		</li>
	</ul>

	<h2>professional service.</h2>
	<h3>reviewing</h3>
	<div
		id="review-summary-vis"
		on:mousemove={onMousemove}
		bind:this={div}
		role="img"
	></div>

	<h3>other</h3>
	<ul class="basic-list">
		<li>EuroVis 2018: Fast Forward Chair, Student Volunteer</li>
		<li>PacificVis 2025: Program Committee</li>
		<li>IEEE VIS 2025: Program Committee</li>
	</ul>

	<h2>talks.</h2>
	<h2>teaching.</h2>
	<h2>publications.</h2>
	<p>
		See <a href="/publications">/publications</a> or
		<a href="#">Google Scholar</a>.
	</p>
</div>

<style>
	* {
		font-family: "Dosis", sans-serif;
	}

	/*h2 {*/
	/*	margin-top: 0;*/
	/*}*/

	#container {
		width: 800px;
	}

	#review-summary-vis {
		width: 600px;
	}

	.cv-item {
		/*background-color: red;*/
		margin: 10px 0 10px 0;
		display: flex;
		gap: 1rem;
	}
	.date-column {
		/*background-color: red;*/
		flex: 1;
	}
	.item-details {
		flex: 4;
	}
	.basic-list {
		list-style-type: none;
	}
	.basic-list li {
		margin: 10px 0 10px 0;
	}
</style>
