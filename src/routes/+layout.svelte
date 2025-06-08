<svelte:head>
    <title>
        {title}
    </title>
</svelte:head>

<script lang="ts">
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte"
    import {page} from "$app/state";
    import { afterNavigate } from "$app/navigation";

	let { children } = $props();
    const appName = "Ren and the Stimpies";

    const getTitle = () => {
        return [appName, ...page.url.pathname.split("/").slice(1).map((s) => s.charAt(0).toUpperCase() + s.slice(1))].filter(Boolean).join(" - ");
    }
    
    let title = $state( getTitle() );

    afterNavigate(() => {
		title = getTitle();
	});
</script>

<div class="page">

    <Header/>

    <div class="page-content">
        {@render children()}
    </div>

    <Footer/>
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
        --color-primary: #cc0033;
        --color-secondary: #bb0099;

        --container-width: 90%;
        --container-max-width: 1000px;
    }

    :global {
        body {
            font-family: 'Perfect DOS VGA 437';
            font-size: 1.5em;
            color: var(--color-text);
            background-color: var(--color-background);
            margin: 0;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Alagard';
            font-size: 1em;
        }

        h1 {
            font-size: clamp(2em, 15vw, 3em);
            margin: .5em 0 .25em 0;
            text-align: center;
        }

        h2 {
            font-size: 2em;
            margin: .4em 0 0.25em 0;
        }

        h3 {
            font-size: 1.5em;
            margin: .4em 0 0.25em 0;
        }

        @media (max-width: 768px) {
            body {
                font-size: 1.2em;
            }
        }
    }

    .page {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100vh;
        margin: 0;
    }

    .page-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: left;
        width: var(--container-width);
        max-width: var(--container-max-width);
    }
</style>