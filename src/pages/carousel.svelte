<script>
    import Card from '../components/Card.svelte';
</script>

<style>
    nav {
        width: min-content;
        margin: auto;
        height: 20rem;
        display: flex;
        overflow-x: visible;

        transition: all 0.5s;

        animation: 26s linear slide infinite;

        background-color: var(--background-contrast);

        /* Fix jitter on some browsers. */
        animation-timing-function: steps(4800);
    }

    nav:hover {
        animation-play-state: paused;

        
    }

    @keyframes slide {
  		100% {
            translate: -50% 0;
        }
	}
</style>

<nav>
    <!--Duplicate elements-->
    {#each new Array(2) as _}
    <Card subtitle="A language with a LISP-like syntax." href="https://github.com/T-O-R-U-S/Shrimp3" title="Shrimp3">
        <code>
            <pre>@main() &lbrace;
    decl x [1 2 3 add(4 4)]
    x[3] -&gt; y
    println(x) # Outputs 8. #
&rbrace;</pre>
        </code>
    </Card>
    <Card subtitle="A social media website with a sprinkle on top."   title="Donut Planet"        >
        Donut Planet has no front-end yet!
    </Card>
    <Card subtitle="A fantasy console that runs on bytecode."         title="ATC Fantacy Console" >
        TODO (maybe add a webgpu demo?)
    </Card>
    <Card subtitle="A JavaScript preprocessor with syntactic sugar."  title="KongScript"          >
        <code>
            <pre>let add = (x y) -> x + y

console.log(add(3 4))</pre>
        </code>
    </Card>
    <Card title="Ipsum"> TODO </Card>
    <Card title="Dolor"> TODO </Card>
    {/each}
</nav>