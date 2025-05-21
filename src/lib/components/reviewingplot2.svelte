<script lang="ts">
	import * as Plot from "@observablehq/plot";
	import reviewsData from "$lib/data/reviews.json";

	let div: HTMLDivElement;

	let tidyReviews = reviewsData.reviews.map((r) => ({
		venue: r.venue,
		year: r.year,
		track: r.track,
		submissionsNum: r.submissions.length,
	}));

	$: {
		div?.firstChild?.remove(); // remove old chart, if any
		div?.append(
			Plot.plot({
				height: 200,
				x: { tickFormat: "d", label: null },
				y: { label: "Reviews", grid: true },
				color: { legend: true },
				marks: [
					Plot.barY(tidyReviews, {
						x: "year",
						y: "submissionsNum",
						fill: "venue",
					}),
				],
			}),
		);
	}
</script>

<div id="review-summary-vis" bind:this={div} role="img"></div>
