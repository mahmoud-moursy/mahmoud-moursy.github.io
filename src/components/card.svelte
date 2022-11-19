<script>
	export let subtitle = "";
	export let href = "#";
	export let title = "Filler";
	export let project = "";

	href = project ? "https://github.com/T-O-R-U-S/" + project : "#";
</script>

<div>
	<a href={href} target="_blank" rel="ugc external noopener noreferrer">
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
		max-width: calc(100% - 3rem);

		@media (prefers-reduced-motion: reduce) {
			animation: none;
			overflow: scroll;
		}

		@media screen and (max-width: 7in) {
			min-width: unset;
			max-width: unset;
			
			border-radius: 0;

			width: 100%;
		}
	
		h2 {
			font-size: 20pt;
		}
	}

	div:hover {
        transition: all 0.5s;

        outline-offset: 1rem;
    }
</style>