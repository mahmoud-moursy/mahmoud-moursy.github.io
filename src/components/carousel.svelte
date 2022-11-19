<script>
	import Card from './card.svelte';
</script>

<style lang="scss">
	div {
		width: 100%;
		overflow-x: hidden;
		overflow-y: hidden;

		height: max-content;

		@media screen and (max-width: 7in) {
			height: 22rem;
		}

		justify-self: flex-end;
	}

	nav {
		margin: auto;
		display: flex;

		width: 100%;
		align-items: center;

		// Mobile only
		overflow-y: hidden;
		animation: 26s linear slide-vertical infinite;
		flex-direction: column;
		height: min-content;
		

		// Desktop
		@media screen and (min-width: 7in) {
			min-height: 20rem;

			align-items: initial;

			width: min-content;

			animation: 26s linear slide infinite;
			overflow-x: hidden;
			flex-direction: initial;
		}

		background-color: var(--background-contrast);
	}

	nav:hover {
		animation-play-state: paused;
	}

	#hint {
		animation: fade ease-in 5s forwards;
		background-color: var(--background-contrast);
		margin: 0;
		text-align: center;
		width: 100%;
	}

	@keyframes fade {
		0% {
			color: var(--text);
		}
		100% {
			color: var(--background-contrast);
		}
	}

	@keyframes slide {
		0% {
			translate: 0 0;
		}
  		100% {
			translate: -50% 0;
		}
	}

	@keyframes slide-vertical {
		0% {
			translate: 0 0;
		}
  		100% {
			translate: 0 -50%;
		}
	}
</style>

<p id="hint">Touch or hover to pause</p>

<div>
<nav>
	<!--Duplicate elements-->
	{#each new Array(2) as _}
	<Card subtitle="A language with a LISP-like syntax." project="Shrimp3" title="Shrimp3">
		<code><pre>
{`@main() {
	decl x [1 2 3 add(4 4)]
	x[3] -> y
	println(x) # Outputs 8. #
}`}</pre></code>
	</Card>
	<Card subtitle="A social media website with a sprinkle on top."   title="Donut Planet">
	   <p>Donut Planet has no front-end yet!</p>
	</Card>
	<Card subtitle="A fantasy console that runs on bytecode."         title="ATC Fantacy Console" project="atc_console" >
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
	<Card subtitle="An OS simulator for a simpler age." title="CronexOS" project="cronexOS-y">

	</Card>
	{/each}
</nav>
</div>