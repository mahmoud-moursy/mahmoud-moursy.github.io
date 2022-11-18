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
	<br>
		<slot />	
</div>

<style lang="scss">
	@use "../styles/mixins.scss" as mixins;

	div {
		@include mixins.outline-hover;

		padding: 3rem;
		margin: 2rem;
		background-color: var(--background);

		text-align: center;

		min-width: 30rem;
		width: min-content;
	
		h2 {
			font-size: 20pt;
		}
	}

	div:hover {
		outline-offset: 1rem;
	}
</style>