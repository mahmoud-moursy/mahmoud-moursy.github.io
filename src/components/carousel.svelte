<script>
	import Card from './card.svelte';
</script>

<style lang="scss">
	div {
		width: 100%;
		overflow-x: hidden;
		overflow-y: hidden;

		min-height: max-content;

		@media screen and (max-width: 7in) {
			height: 20rem;

			border-width: 0;
			border-top-width: 5px;
			border-bottom-width: 5px;

			border-style: solid;
			border-color: var(--accent);
		}

		justify-self: flex-end;
	}

	nav {
		margin: auto;
		display: flex;

		width: 100%;
		align-items: center;

		// Mobile only
		overflow-y: visible;
		animation: 45s linear slide-vertical infinite;
		flex-direction: column;
		height: max-content;

		// Desktop
		@media screen and (min-width: 7in) {
			height: max-content;

			align-items: initial;

			width: min-content;

			animation: 26s linear slide infinite;
			overflow: hidden;
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
			transform: translateX(0);
		}
  		100% {
			transform: translateX(-50%);
		}
	}

	@keyframes slide-vertical {
		0% {
			transform: translateY(0);
		}
  		100% {
			transform: translateY(-50%);
		}
	}
</style>

<p id="hint">Touch or hover to pause</p>

<div>
<nav>
	<!--Duplicate elements-->
	{#each new Array(2) as _}
	<Card subtitle="A language with a LISP-like syntax." project="Shrimp3" title="Shrimp3" >
		<code><pre>
{`@main() {
	decl x [1 2 3 add(4 4)]
	x[3] -> y
	println(x) # Outputs 8. #
}`}</pre></code>
	</Card>
	<Card subtitle="A fantasy console that runs on bytecode."         title="ATC Fantacy Console" project="atc_console" >
		<p>
			The ATC Fantasy console has a whole ecosystem of applications; the <a href="https://github.com/T-O-R-U-S/bytecode_byter">ATC Byter</a> for 
			bytecode analysis, the <a href="https://github.com/T-O-R-U-S/asc_lang">ASC language</a> for writing code for the system and the 
			<a href="https://github.com/T-O-R-U-S/atc_console">console emulator</a>.
		</p>
	</Card>
	<Card subtitle="A barebones TUI library for barebones environments" title="Tuit" project="tuit">
		<p>
			Tuit is the TUI library for the hard-mode Rust user. It is a `no_std`, `no_alloc` library that makes the most out of its constraints.
		</p>
	</Card>
	<Card subtitle="An OS simulator for a simpler age." title="CronexOS" project="cronexOS-y">
		<p>
			CronexOS is a web-browser simulation OS that takes after the likeness of AmigaOS and Windows 
			9x to create a fun experience.
			Features include: <br>
		</p>
		<ul>
			<li>Changing backgrounds</li>
			<li>Text editor</li>
			<li>"Web" browser</li>
			<li>An application menu</li>
		</ul>
	</Card>
	{/each}
</nav>
</div>
