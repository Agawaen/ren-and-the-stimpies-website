<script lang="ts">
    import Navbar from "$lib/Navbar.svelte";
	let { children } = $props();
</script>

<div class="page">
    <title>
        Ren and the Stimpies
    </title>

    <Navbar/>

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

    :root {
        --color-background: #000;
        --color-text: #eee;
        --color-primary: crimson;
    }

    :global {
        body {
            font-family: 'Perfect DOS VGA 437';
            font-size: 1.5em;
            color: var(--color-text);
            background-color: var(--color-background);
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Alagard';
            font-size: 1em;
        }

        h1 {
            font-size: 3em;
            margin: .5em 0 .25em 0;
            text-align: center;
        }

        h2 {
            font-size: 2em;
            margin: .4em 0 0 0;
        }

        h3 {
            font-size: 1.5em;
            margin: .3em 0 0 0;
        }
    }

    .page {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>