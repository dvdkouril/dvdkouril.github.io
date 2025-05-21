<script lang="ts">
	//import { page } from '$app/stores';
	let { children } = $props();

	//const showHeaderFor = ["/", "cv"];
	//const showHeader = derived(page, ($page) => {
	//	$page.url.
	//});
	const currentPath: string = "/";
</script>

<div id="header">
	<div id="name-title">
		<h1>DAVID KOUŘIL.</h1>
		<h2><pre>David Kou\v{"{"}r{"}"}il</pre></h2>
	</div>
	<div style="width: 3px; height: 80px; background-color: #aaaaaa;"></div>
	<nav id="menu">
		<ul>
			<li><a href="/" class:selected={currentPath === "/"}>home.</a></li>
			<li>
				<a href="/cv" class:selected={currentPath === "/cv"}>cv.</a>
			</li>
			<!--<li>
				<a href="/projects" class:selected={currentPath === "/projects"}
					>projects.</a
				>
			</li>-->
		</ul>
	</nav>
</div>
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
</style>
