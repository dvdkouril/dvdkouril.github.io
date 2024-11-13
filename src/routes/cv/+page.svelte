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
				// color: {
				// 	scheme: "Spectral",
				// 	legend: "ramp",
				// 	label: "Venues",
				// },
				color: {
					legend: true,
					scheme: "Spectral",
				},
				marks: [
					Plot.barY(
						reviewsData,
						Plot.groupX(
							{ y: "count" },
							{ x: "date", fill: "venue" },
						),
					),
				],
			}),
		);
	}
</script>

<h1>cv.</h1>
<p>experience</p>

<h2>community service</h2>
<h3>reviewing</h3>
<div on:mousemove={onMousemove} bind:this={div} role="img"></div>
