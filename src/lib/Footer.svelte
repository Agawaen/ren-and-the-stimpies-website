<script lang="ts">
	import Instagram from "$lib/icons/Instagram.svelte";
    import Tiktok from "./icons/Tiktok.svelte";
    import Youtube from "./icons/Youtube.svelte";
</script>

<footer>
    <hr class="line">
    <div class="content">
        <h3 class="name">Ren and<br>the Stimpies</h3>
        <a href="https://www.instagram.com/renandthestimpies/"><Instagram class="icon"/></a>
        <a href="https://www.instagram.com/renandthestimpies/"><Tiktok class="icon"/></a>
        <a href="https://www.instagram.com/renandthestimpies/"><Youtube class="icon"/></a>
    </div>
</footer>

<style>
    footer {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
        margin-top: auto;
    }

    .name {
        margin: 0;
        margin-right: auto;
    }

    .line {
        width: 100%;
        height: 1px;
        border-width: 0;
        margin: 1em 0 0 0;
        background-color: var(--color-text);
    }

    .content {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1em;
        width: 50%;
        min-width: 500px;
        padding: 1em 0;
    }

    :global(.icon) {
        width: 2em;
        height: 2em;
        fill: var(--color-text);
    }
</style>