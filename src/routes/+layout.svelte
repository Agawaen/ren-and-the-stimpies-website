<script lang="ts">
	let { children } = $props();
</script>

<div>
    <title>
        Ren and the Stimpies
    </title>
    <h1>
        Ren and the Stimpies
    </h1>
    <nav>
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/music">Music</a>
        <a href="/contact">Contact</a>
    </nav>

    {@render children()}

</div>

<style>
    @font-face {
        font-family: 'Alagard';
        font-style: normal;
        font-display: swap;
        font-weight: 400;
        src: url($lib/fonts/alagard.ttf);
    }

    @font-face {
        font-family: 'Perfect DOS VGA 437';
        font-style: normal;
        font-display: swap;
        font-weight: 400;
        src: url('$lib/fonts/Perfect DOS VGA 437.ttf');
    }

    :global(body) {
        font-family: 'Perfect DOS VGA 437';
        font-size: 1.5em;
    }

    :global(h1, h2, h3, h4, h5, h6) {
        font-family: 'Alagard';
        font-size: 1em;
    }

    :global(h1) {
        font-size: 3em;
        margin: .5em 0 .25em 0;
        text-align: center;
    }

    :global(h2) {
        font-size: 2em;
        margin: .4em 0 0 0;
    }

    :global(h3) {
        font-size: 1.5em;
        margin: .3em 0 0 0;
    }

    div {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>