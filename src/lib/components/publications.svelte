<script lang="ts">
	import { pubs } from "$lib/data/publications";
	import PublicationsGroup from "./publicationsgroup.svelte";

	let preprints = $derived(pubs.filter((p) => p.type === "preprint"));
	let peerReviewed = $derived(pubs.filter((p) => p.type === "peer-reviewed"));
	let otherPubs = $derived(
		pubs.filter((p) => p.type !== "peer-reviewed" && p.type !== "preprint"),
	);
</script>

<p>
	See on
	<a href="https://scholar.google.com/citations?user=dZxZ__wAAAAJ&hl=en"
		>Google Scholar</a
	>.
</p>
<h3>preprints.</h3>
<PublicationsGroup pubs={preprints} />

<h3>peer-reviewed.</h3>
<PublicationsGroup pubs={peerReviewed} />

<h3>other.</h3>
<PublicationsGroup pubs={otherPubs} />
