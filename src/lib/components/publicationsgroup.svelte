<script lang="ts">
	import type { Publication } from "$lib/data/publications";

	let { pubs }: { pubs: Publication[] } = $props();
</script>

<div>
	{#each pubs.sort((a, b) => a.year - b.year).reverse() as pub}
		<p>
			"{pub.title}",
			<br />
			{@html pub.authors
				.map((a) => (a === "D. Kouřil" ? `<strong>${a}</strong>` : a))
				.join(", ")}
			<br />
			<i>{pub.journal}</i>,
			{pub.year}.
		</p>
	{/each}
</div>
