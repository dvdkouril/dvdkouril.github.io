<script lang="ts">
	import { onMount } from "svelte";
	import { AxisX, Dot, Plot, Rect } from "svelteplot";
	import { z } from "zod";
	import { timeFormat, timeParse } from "d3-time-format";

	let ninaDayLogSchema = z.object({
		days: z.array(
			z.object({
				date: z
					.string()
					.date()
					.transform((s) => new Date(s)),
				bedtime: z.string().transform((s) => timeParse("%I:%M%p")(s)),
				wakeuptime: z
					.string()
					.transform((s) => timeParse("%I:%M%p")(s)),
				wakings: z.array(z.string()).nullish(),
			}),
		),
	});

	type SleepData = z.infer<typeof ninaDayLogSchema>;

	let ninaData: SleepData;

	onMount(async () => {
		const response = await fetch(
			"https://raw.githubusercontent.com/dvdkouril/visualnination/main/data/nina.json",
		);
		if (!response.ok) {
			throw new Error(`Response status: ${response.status}`);
		}

		const sleepDataRaw = await response.json();
		console.log("sleepDataRaw", sleepDataRaw);
		ninaData = ninaDayLogSchema.parse(sleepDataRaw);
		console.log("ninaData", ninaData);
	});

	const tickFormat = (date: Date | string | undefined) => {
		//tickFormat: d3.timeFormat("%I %p")
		return date ? timeFormat("%I %p")(date) : "err";
	};
</script>

<!--<Plot grid x={{ tickFormat: tickFormat }}>-->
<Plot
	grid
	x={{
		//domain: [
		//	new Date("2025-01-01T00:00:00"),
		//	new Date("2025-01-01T23:00:00"),
		//],
		tickFormat(d) {
			return "hi";
		},
		//x: {
		//    tickFormat(d) {
		//      const [a, b] = d.toLocaleString("de-DE").split(",");
		//      return `${a}\n${b}`;
		//    }
		//}
		tickRotate: -90,
	}}
	y={{ tickFormat: () => "Hi" }}
>
	{#if ninaData}
		<Dot data={ninaData.days} x="wakeuptime" y="date" />
		<!--<Rect
			data={ninaData.days}
			x1="wakeuptime"
			x2="bedtime"
			y="date"
			fill="red"
		/>-->
		<Dot data={ninaData.days} x="bedtime" y="date" stroke={"red"} />
	{/if}
</Plot>
