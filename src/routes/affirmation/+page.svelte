<script lang="ts">
	import { onMount } from "svelte";

	/**
	 * @param {HTMLElement} parentEl
	 * @param {number} mouseX
	 * @param {number} mouseY
	 */
	function makeGraphic(parentEl: HTMLElement, mouseX = 1, mouseY = 1) {
		const svgEl = document.createElementNS(
			"http://www.w3.org/2000/svg",
			"svg",
		);
		svgEl.setAttribute("width", "100%");
		svgEl.setAttribute("height", "100%");
		//svgEl.setAttribute("width", "100vw");
		//svgEl.setAttribute("height", "100vh");
		//svgEl.setAttribute("viewBox", "0 0 300 100");
		svgEl.setAttribute("style", "font-family: sans-serif; display: block;");

		const numOfGhosts = 20;
		//const text = "get it done.";
		//const text = "finish it.";
		const text = "i can do hard things.";
		const docW = document.documentElement.clientWidth;
		const docH = document.documentElement.clientHeight;
		const x = mouseX - docW / 2;
		const y = mouseY - docH / 2;
		const dirMagnitude = Math.sqrt(x * x + y * y);
		const offsetDirectionX = x / dirMagnitude;
		const offsetDirectionY = y / dirMagnitude;
		console.log(`${offsetDirectionX}, ${offsetDirectionY}`);
		const offsetSpacing = 2;
		for (let i = 0; i < numOfGhosts; i++) {
			const offset = i * offsetSpacing;
			const textTest = document.createElementNS(
				"http://www.w3.org/2000/svg",
				"text",
			);
			textTest.textContent = text;
			textTest.setAttribute("x", `${50 + offset * offsetDirectionX}`);
			textTest.setAttribute("y", `${200 + offset * offsetDirectionY}`);
			textTest.setAttribute("font-size", `${160}`);
			textTest.setAttribute("fill", "none");
			textTest.setAttribute("stroke", "green");
			textTest.setAttribute("stroke-width", `${0.3}`);
			svgEl.appendChild(textTest);
		}

		parentEl.replaceChildren();
		parentEl.appendChild(svgEl);

		//return svgEl;
	}

	/**
	 * @param {MouseEvent} event
	 */
	function handleMouseMove(event: MouseEvent) {
		const x = event.clientX;
		const y = event.clientY;
		console.log(`mouse: ${x}, ${y}`);

		makeGraphic(appEl, x, y);
	}

	onMount(() => {
		console.log("sup");
		makeGraphic(appEl);

		document.addEventListener("mousemove", handleMouseMove);
	});

	let appEl: HTMLElement;
</script>

<div bind:this={appEl} style="width: 100vw; height: 100vh">
	<!--<svg></svg>-->
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
	}
</style>
