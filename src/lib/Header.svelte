<!-- <a class="link" href="/" class:active={currentPath == "/"}>{currentPath == "/" ? "<" : ""}Home{currentPath == "/" ? ">" : ""}</a> -->

<script lang="ts">
    import { page } from "$app/state";
    import { afterNavigate } from "$app/navigation";

    const navLinks = [
        {href: "/", label: "Home"},
        {href: "/about", label: "About"},
        {href: "/music", label: "Music"},
        {href: "/contact", label: "Contact"}
    ];
	let currentPath = page.url.pathname;

	afterNavigate(() => {
		currentPath = page.url.pathname;
	});

</script>

<header>
    <h1>
       Ren and the Stimpies
    </h1>
    <nav>
        {#each navLinks as navLink}
            {#if currentPath == navLink.href}
                <a class="link active" href={navLink.href}>{`<${navLink.label}>`}</a>
            {:else}
                <a class="link" href={navLink.href}>{navLink.label}</a>
            {/if}
        {/each}
    </nav>
    <hr class="line first-line"/>
    <hr class="line second-line"/>
</header>

<style>
    header {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
        margin: 0 0 0.5em 0;
    }

    nav {
        margin: 0 0 0.1em 0;
    }

    .link {
        color: inherit;
        text-decoration: inherit;
        margin: 0 0.5em;
    }

    .link:hover {
        text-decoration: underline;
    }

    .active {
        color: var(--color-primary);
    }

    .line {
        width: 100%;
        height: 1px;
        border-width: 0;
        margin: 3px;
    }

    .first-line {
        background-color: var(--color-primary);
    }

    .second-line {
        background-color: var(--color-secondary);
    }
</style>