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

	//~ test
	//tidyReviews.push({
	//	venue: "bla bla",
	//	year: 2026,
	//	track: "whatever",
	//	submissionsNum: 50,
	//});

	type ReviewEntry = {
		venue: string;
		year: number;
		track: string;
		submissionsNum: number;
	};

	const findMaxNumberOfReviews = (reviews: ReviewEntry[]): number => {
		const yearSums = new Map<number, number>();
		for (const review of reviews) {
			const currVal = yearSums.get(review.year);
			if (currVal) {
				yearSums.set(review.year, currVal + review.submissionsNum);
			} else {
				yearSums.set(review.year, review.submissionsNum);
			}
		}
		return Math.max(...yearSums.values());
	};

	const maxReviewsOverall = findMaxNumberOfReviews(tidyReviews);

	$: {
		div?.firstChild?.remove(); // remove old chart, if any
		div?.append(
			Plot.plot({
				height: 200,
				x: { tickFormat: "d", label: null },
				//y: { label: "Reviews", grid: true },
				y: { label: "Reviews", grid: true, ticks: maxReviewsOverall },
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
