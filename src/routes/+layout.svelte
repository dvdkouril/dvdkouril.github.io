<script lang="ts">
	import { page } from "$app/state";
	let { children } = $props();

	const showHeaderFor = ["/", "/cv", "/work", "/thingsimade"];
	const pageUrl = $derived(page.url.pathname);
	const showHeader = $derived(showHeaderFor.some((v) => pageUrl === v));
</script>

{#if showHeader}
	<div id="header">
		<div id="name-title">
			<h1>DAVID KOUŘIL.</h1>
			<h2><pre>David Kou\v{"{"}r{"}"}il</pre></h2>
		</div>
		<div style="width: 2px; height: 80px; background-color: #000;"></div>
		<nav id="menu">
			<ul>
				<li>
					>
					<a href="/">home.</a>
					<!--<a href="/" class:selected={currentPath === "/"}>home.</a>-->
				</li>
				<li>
					>
					<a href="/cv">cv.</a>
					<!--> <a href="/cv" class:selected={currentPath === "/cv"}>cv.</a>-->
				</li>
				<!--<li>
				<a href="/projects" class:selected={currentPath === "/projects"}
					>projects.</a
				>
			</li>-->
			</ul>
		</nav>
	</div>
{/if}
{@render children()}

<style>
	h1 {
		font-family: "Dosis", sans-serif;
		padding-bottom: 0;
		margin-bottom: 0;
		margin-top: 0;
		font-size: 2.2em;
	}

	h2 {
		font-family: "Dosis", sans-serif;
		color: #aaaaaa;
		padding-top: 0;
		margin-top: 0;
		margin-bottom: 0;
		font-size: 1.65em;
	}
	h2 > pre {
		font-family: "Dosis", sans-serif;
		padding-top: 0;
		margin-top: 0;
		margin-bottom: 0;
	}
	#header {
		display: flex;
		gap: 1em;
	}
	#menu {
		font-family: "Dosis", sans-serif;
		font-size: 1.2em;
	}

	#menu ul {
		list-style: none;
		padding: 0;
		margin: 0;
	}

	#menu ul li {
		margin: 0;
	}

	#menu a {
		/*background-color: #aaaaaa;*/
		/*color: black;*/
		/*text-decoration: none;*/
	}
</style>
