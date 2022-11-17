<script>
	export let subtitle = "";
	export let href = "";
	export let title = "Filler";
</script>

<div>
	<a href={href} target="_blank" rel="noopener noreferrer">
		<h2>{title}</h2>
		<p>{subtitle}</p>
	</a>
		<slot />	
</div>

<style lang="scss">
	@import '../styles/variables.scss';

	div {
		padding: 3rem;
		margin: 2rem;
		background-color: var(--background);

		outline-color: $accent;
		outline-width: 5px;
		outline-style: solid;
		outline-offset: 0.5rem;
		
		border-radius: 1rem;

		text-align: center;

		min-width: 30rem;
		width: min-content;

		transition: all 0.5s;
	}

	div:hover {
		outline-offset: 1rem;
	}
</style>