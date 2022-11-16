<script>
	export let subtitle = "";
	export let href = "";
	export let title = "Filler";
</script>

<div>
	<a href={href}>
		<h2>{title}</h2>
		<p>{subtitle}</p>
	</a>
		<slot />	
</div>

<style>
	div {
		padding: 3rem;
		margin: 2rem;
		background-color: white;

		outline-color: var(--accent);
		outline-width: 5px;
		outline-style: solid;
		outline-offset: 0.5rem;
		
		border-radius: 1rem;

		text-align: center;

		min-width: 30rem;
		width: min-content;
	}
</style>