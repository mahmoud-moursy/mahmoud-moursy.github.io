<script>
	export let subtitle = "";
	export let href = "#";
	export let title = "Filler";

	let rel = href == "#" ? "nofollow" : "ugc";
</script>

<div>
	<a href={href} target="_blank" rel={`${rel} noopener noreferrer`}>
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
		max-width: calc(100vw - 3rem);

		// Remove theming for Safari (which does not render outline radii correctly.)
		_::-webkit-full-page-media, _:future, :root {
			outline-style: none;
		}
	
		h2 {
			font-size: 20pt;
		}
	}

	div:hover {
		outline-offset: 1rem;
	}
</style>