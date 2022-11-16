<script>
    import Card from '../components/Card.svelte';
</script>

<style>
    nav {
        display: flex;
    }

    nav {
        width: 100%;
        height: 20rem;
        display: flex;
        overflow-x: visible;

        animation: 10s linear slide infinite;
    }

    @keyframes slide {
  		100% {
            translate: -100% 0;
        }
	}
</style>

<nav>
    <Card subtitle="A language with a LISP-like syntax." href="#" title="Shrimp3">
        <code>
            <pre>
@main() &lbrace;
decl x [1 2 3 add(4 4)]
x[3] -&gt; y
println(x) # Outputs 8. #
&rbrace;
            </pre>
        </code>
    </Card>
    <Card subtitle="A social media website with a sprinkle on top."  href="#" title="Donut Planet"        ></Card>
    <Card subtitle="A fantasy console that runs on bytecode."        href="#" title="ATC Fantacy Console" ></Card>
    <Card subtitle="A JavaScript preprocessor with syntactic sugar." href="#" title="KongScript"          ></Card>
    <Card href="#" title="Ipsum"></Card>
    <Card href="#" title="Dolor"></Card>
</nav>