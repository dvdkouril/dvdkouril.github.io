<script>
	import week1thumb from '$lib/images/hdvcc/thumbnails/hdvcc-week1.png';
</script>
<svelte:head>
	<title>hdvcc</title>
	<meta name="description" content="like a book club, but with coding." />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true">
	<link href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap" rel="stylesheet">
</svelte:head>

<h1>hidive coding club.</h1>
<div id="container">
	<ul>
		<li>we meet every week for 1 hour.</li>
		<li>we go through a coding book and implement the material.</li>
		<li>we have a rotating schedule: one person from the group is typing, others are supporting.</li>
		<li>each week’s work ends up as a pull request. all participants are tagged in the commit.</li>
		<li>you should not do extra work outside of the club meeting.</li>
	</ul>

	<h2>currently.</h2>
	<p>
		Implementing <a href="https://raytracing.github.io/books/RayTracingInOneWeekend.html">Ray Tracing in One Weekend</a> using <a href="http://ziglang.org">zig</a>.
	</p>
	<p>
		repository: <a href="https://github.com/dvdkouril/hdvcc">github.com/dvdkouril/hdvcc</a>.
		</p>

	<h2>meetings.</h2>
	<h3>next</h3>
	<p>Thursday May 23, 2024.</p>
	<h3>past</h3>
	<p><b>Thursday May 16, 2024.</b><br/>
	<i>Video: <a href="https://youtu.be/GXSmvagvxbY">youtube.com/watch?v=GXSmvagvxbY</a></i><br/>
	<i>Code: <a href="https://github.com/dvdkouril/hdvcc/pull/1">github.com/dvdkouril/hdvcc/pull/1</a></i><br/>
	Setting up: downloading and installing zig, trying to fix david's zls in neovim, exploring file structure are zig init, figuring out how to write to standard output.
	<img class="thumb" width=600 src={week1thumb} alt="screenshot of two windows side-by-side, one is an online book and the other is a text editor"/>
	</p>
</div>


<style>
* {
	font-family: "Dosis", sans-serif;
}
p, ul {
	font-size: 1.2em;
}
#container {
	width: 600px;
	text-align: justify;
	}
p {
	margin-left: 20px;
}
ul {
	list-style-type: "\2328\FE0F"; 
}
li {
	padding-left: 10px;
	margin-bottom: 5px;
}
.thumb {
	margin-top: 15px;
}
</style>
