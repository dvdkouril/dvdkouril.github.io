<script lang="ts">
	type Item = {
		title: string;
		links: {
			link: string;
			name: string;
		}[];
		tags: Tags[];
		year: number;
	};

	type Tags = "hidive" | "personal";

	const stuff: Item[] = [
		{
			title: "HUROS 2024 poster",
			links: [
				{
					link: "https://www.dropbox.com/scl/fi/gegw3bq5kvinyc2eeoa9q/poster-huros_hidivelab.pdf?rlkey=06uopvugnso3pvbk3jvp8ojam&dl=0",
					name: "poster",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
		{
			title: "HUROS 2023 poster",
			links: [
				{
					link: "https://www.dropbox.com/scl/fi/hrvfjf21uch0517z6ya6v/poster-huros_hidivelab.pdf?rlkey=e5n30h65sxwhlymaf8mg23l71&dl=0",
					name: "poster",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
		{
			title: "4DN annual meeting 2024 poster",
			links: [
				{
					link: "https://www.dropbox.com/scl/fi/rrmnmq1vdbtywg32xv5wr/poster-maybe-final2.pdf?rlkey=gk3djgrz17xseohsp9wdgwatq&dl=0",
					name: "poster",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
		{
			title: "HIDIVE zoom background",
			links: [
				{
					link: "http://www.davidkouril.com/hidive-zoom-bg/",
					name: "app",
				},
				{
					link: "https://github.com/dvdkouril/hidive-zoom-bg/",
					name: "code",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
		{
			title: "anywidget setup: developing both the library and the widget",
			links: [{ link: "", name: "video" }],
			tags: ["hidive"],
			year: 2025,
		},
		{
			title: "visualnination: visualization of nina's sleep",
			links: [
				{
					link: "https://github.com/dvdkouril/visualnination",
					name: "code",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
		{
			title: "quak: Add hovered value label for Histogram plot",
			links: [
				{
					link: "https://github.com/manzt/quak/pull/32",
					name: "PR",
				},
			],
			tags: ["hidive"],
			year: 2024,
		},
	];

	const stuff2024 = stuff.filter((i) => i.year === 2024);
	const stuff2025 = stuff.filter((i) => i.year === 2025);
</script>

<h1>small things i've made</h1>
<p>
	a list of small (or big) things i've created. no rules, mostly stuff i'm
	just proud of.
</p>
<p>personal stuff omitted.</p>
<h2>2025</h2>
<ul>
	{#each stuff2025 as thing}
		<li>
			[{#each thing.links as link}
				<a href={link.link}>{link.name}</a>
			{/each}] {thing.title}
			{#each thing.tags as tag}
				<span style="border: 1px solid black;">{tag}</span>
			{/each}
		</li>
	{/each}
</ul>
<h2>2024</h2>
<ul>
	{#each stuff2024 as thing}
		<li>
			[{#each thing.links as link}
				<a href={link.link}>{link.name}</a>
			{/each}] {thing.title}
			{#each thing.tags as tag}
				<span style="border: 1px solid black;">{tag}</span>
			{/each}
		</li>
	{/each}
</ul>
