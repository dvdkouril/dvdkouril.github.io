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
			<br />
			<a href="https://doi.org/{pub.doi}">{pub.doi}</a>
		</p>
	{/each}
</div>

<style>
	a {
		color: black;
		font-size: 90%;
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
</style>
