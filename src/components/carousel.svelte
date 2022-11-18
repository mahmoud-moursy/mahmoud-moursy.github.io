<script>
	import Card from './card.svelte';
</script>

<style lang="scss">
	nav {
		margin: auto;
		min-height: 20rem;
		display: flex;

		transition: all 0.5s;

		// Mobile only
		width: 100vw;
		overflow-x: scroll;
		
		// Desktop
		@media screen and (min-width: 12in) {
			animation: 26s linear slide infinite;
			overflow-x: hidden;
			width: min-content;
		}

		background-color: var(--background-contrast);
	}

	nav:hover {
		animation-play-state: paused;
	}

	@keyframes slide {
		0% {
			translate: 0 0;
		}
  		100% {
			translate: -50% 0;
		}
	}
</style>

<nav>
	<!--Duplicate elements-->
	{#each new Array(2) as _}
	<Card subtitle="A language with a LISP-like syntax." href="https://github.com/T-O-R-U-S/Shrimp3" title="Shrimp3">
		<code><pre>
{`@main() {
	decl x [1 2 3 add(4 4)]
	x[3] -> y
	println(x) # Outputs 8. #
}`}</pre></code>
	</Card>
	<Card subtitle="A social media website with a sprinkle on top."   title="Donut Planet"        >
	   <p>Donut Planet has no front-end yet!</p>
	</Card>
	<Card subtitle="A fantasy console that runs on bytecode."         title="ATC Fantacy Console" >
		<p>TODO (maybe add a webgpu demo?)</p>
	</Card>
	<Card subtitle="A JavaScript preprocessor with syntactic sugar."  title="KongScript"          >
		<code>
			<pre>let add = (x y) -> x + y

console.log(add(3 4))</pre>
		</code>
	</Card>
	<Card subtitle="A small operating system for a small world." title="picOS">
		Add a screenshot?
	</Card>
	<Card title="Dolor">

	</Card>
	{/each}
</nav>